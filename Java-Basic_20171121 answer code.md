Generics & Collection Framework: Exercise
=============

## Tue, Nov 21st, 2017

## 문서 에디터 '단어 검색' 기능
#### 출처: SCSC, 갓필식, java SIG 2017_1


    package javaSIG_2017Fall;
    
    import java.io.IOException;
    import java.nio.file.Files;
    import java.nio.file.Paths;
    import java.util.*; //HashSet, Scanner 등을 import함.
    

    public class Shakespeare {

     public static void main(String[] args) {
          boolean externalLoop = true;
          System.out.print("Document Search\n-------start-------\n\n");
          while(externalLoop){
              Scanner sc = new Scanner(System.in);
              System.out.print("Enter document path: "); //shakespeare.txt
              String dataPath = sc.nextLine();
              List<String> data;
              if(dataPath.equals("quit_document")){
                  externalLoop=false;
                  break;
              } else{
                  try {
                      data = Files.readAllLines(Paths.get(dataPath));
                  } catch(IOException ex) {
                      System.out.println("해당 파일은 존재하지 않습니다.");
                      throw new RuntimeException(ex);
                  }
              }

              boolean internalLoop = true;
              while(internalLoop){
                  System.out.print("Enter word: ");
                  String query = sc.nextLine();

                  if(query.equals("quit_document")){
                      externalLoop=false;
                      break;
                  } else if(query.equals("quit_word")){
                      internalLoop=false;
                      break;
                  } else{
                      TextSearch textSearch = new TextSearch(data);
                      SearchResult result = textSearch.search(query);
                      result.printWithUnderline();
                      System.out.println();
                  }
              }
          }
          System.out.print("-------quit-------");
       }
 	}

    class SearchResult {
        private String query;
        private HashSet<Integer> lines;
        private List<String> data;

        public SearchResult(String query, HashSet<Integer> lines, List<String> data) {
            this.query = query;
            this.lines = lines;
            this.data = data;
        }

        public void print() {
            if(lines==null){
                System.out.println("Nothing found... :(");
                return;
            }
            System.out.print(query+" occurs in "+lines.size()+ "lines\n");

            HashSet<Integer> set = lines;
            Integer[] sorted = new Integer[set.size()];
            set.toArray(sorted);
            Arrays.sort(sorted);
            for (int n : sorted) {
                System.out.println("(line "+n+") "+data.get(n));
            }

        }

        public void printWithUnderline() {
            if(lines==null){
                System.out.println("Nothing found... :(");
                return;
            }
            System.out.print(query+" occurs in "+lines.size()+ " lines\n");

            HashSet<Integer> set = lines;
            Integer[] sorted = new Integer[set.size()];
            set.toArray(sorted);
            Arrays.sort(sorted);
            for (int n : sorted) {
                String line = "(line "+n+") "+data.get(n);
                System.out.println(line);
                for(int i=0; i<line.indexOf(query, 5);i++){
                    System.out.print(" ");
                }
                for(int i=0; i<query.length();i++){
                    System.out.print("*");
                }
                System.out.print("\n");
            }
        }
    }

    class TextSearch {
        private List<String> data;
        private HashMap<String, HashSet<Integer>> dict = new HashMap<>();

        public TextSearch(List<String> data) { 
            this.data = data;
            for(int i=0;i<data.size();i++){
                String originalStr = data.get(i);
                String strWithoutPunctuation = originalStr.replace("[^\\w\\s]", "");
                String[] strSplit = strWithoutPunctuation.split(" ");

                for(String word : strSplit){
                    if(dict.containsKey(word)==false){
                        dict.put(word, new HashSet<Integer>());
                    }
                    dict.get(word).add(i);
                }
            }
        }

        public SearchResult search(String word) {
            HashSet<Integer> lines = dict.get(word);
            SearchResult searchResult = new SearchResult(word, lines, data);
            return searchResult;
        }
    }