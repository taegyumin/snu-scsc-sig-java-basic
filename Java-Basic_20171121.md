Generics & Collection Framework: Exercise
=============

## Tue, Nov 21st, 2017

## 문서 에디터 '단어 검색' 기능
#### 출처: SCSC, 갓필식, java SIG 2017_1
  
이런 걸 만들 겁니다.


	Document Search
    -------start-------
    
	Enter document path: shakespeare.txt
	Enter word: foolish
    
	foolish occurs 81 times
	(line 2641) Dissuade one foolish heart from serving thee,
	(line 5317) heed of the allurement of one Count Rousillon, a foolish idle
	(line 8024) CLEOPATRA. For the most part, too, they are foolish that are so.
	(line 11091) To bring again these foolish runaways. Exeunt
	(line 12265) You foolish shepherd, wherefore do you follow her,
	(line 12467) being taken with the cramp, was drown'd; and the foolish
	...

	Enter document path: shakespeare.txt
	Enter word: congratulations
	Nothing found... :(
    
    Enter document path: shakespeare.txt
	Enter word: quit-word
    
    Enter document path: quit-path
    
	-------quit-------
    

  
  
### 1단계. 단어의 위치(index)를 알아내라.

	public static void main(String[] args){
    
		String str = "You will pay for this foolish behavior.";
    	System.out.println("foolish index: ");
    	/*
    	 * 코드를 채우시오.
    	 */
	}
    
 출력시 콘솔창
	
    foolish index: 22


  
  
### 2단계. 단어에 (별표로) 밑줄을 그어라.

	public static void main(String[] args){
    
		String str = "You will pay for this foolish behavior.";
    	System.out.println(str);
    	/*
    	 * 코드를 채우시오.
    	 */
	}
    
 출력시 콘솔창
	
    You will pay for this foolish behavior.
	                      *******   

  
  
### 3단계. file IO Library를 활용하여 주어진 텍스트 파일의 내용을 콘솔창에 출력하라.

shakespeare.txt

	import java.io.BufferedReader;
	import java.io.BufferedWriter;
    import java.io.IOException;
    import java.io.Scanner;

	public static void main(String[] args){
		/*
    	 *......
		 *......
		 *......
    	 */
	}
    
  
실행시 콘솔창은 아래와 같다. 여기서 shakespeare.txt와 foolish는 키보드를 통해 입력한 문자열이다.


	Document Search
    -------start-------
    
	Enter document path: shakespeare.txt
	Enter word: foolish
    
	foolish occurs 81 times
	(line 2641) Dissuade one foolish heart from serving thee,
	(line 5317) heed of the allurement of one Count Rousillon, a foolish idle
	(line 8024) CLEOPATRA. For the most part, too, they are foolish that are so.
	(line 11091) To bring again these foolish runaways. Exeunt
	(line 12265) You foolish shepherd, wherefore do you follow her,
	(line 12467) being taken with the cramp, was drown'd; and the foolish
	...

	Enter document path: shakespeare.txt
	Enter word: congratulations
	Nothing found... :(
    
    Enter document path: shakespeare.txt
	Enter word: quit-word
    
    Enter document path: quit-path
    
	-------quit-------


  
### java 1.8의 IO Library  
기존의 라이브러리보다 쓰기가 훨씬 쉽다.

	List<String> data;
	try {
		data = Files.readAllLines(Paths.get(dataPath));
	} catch(IOException ex) {
		throw new RuntimeException(ex);
	}
    
	String data;
	try {
		data = new String(Files.readAllBytes(Paths.get(dataPath)));
	} catch(IOException ex) {
		throw new RuntimeException(ex);
	}  
    
    
    
    
  
### 문장부호 없애기: Regex를 이용한다.  

	String strWithoutPunctuation = originalStr.replace("[^\\w\\s]", "");
    
  
  
### sorting

Arrays.sort(Object[] a) 를 사용.

	HashSet<Integer> set = ...;
	Integer[] sorted = new Integer[set.size()];
	set.toArray(sorted);
	Arrays.sort(sorted);
	for (int n : sorted) System.out.println(n);  
    
    
### 추가 구현  

### 각 줄마다 찾은 단어 밑줄쳐주기.

	Enter document path: shakespeare.txt
	Enter word: foolish
	foolish occurs in 81 lines
	(line 2641) Dissuade one foolish heart from serving thee,
				 *******
	(line 5317) heed of the allurement of one Count Rousillon, a foolish idle
								     *******
	(line 8024) CLEOPATRA. For the most part, too, they are foolish that are so.
								*******
	(line 11091) To bring again these foolish runaways. Exeunt
					  *******
	(line 12265) You foolish shepherd, wherefore do you follow her,
			 *******
	(line 12467) being taken with the cramp, was drown'd; and the foolish
								      *******

### End of Document.  
