Java: Exercise
=============
Class and Object
Java Basic Classes
Generics & Collection Framework

# 수능 기념 스페셜 컬렉션

---------

## 1. 모의면접 테스트 생성기
#### #java.util.Random #java.util.Scanner

#### 관문1
자기소개 해보세요.

안 함.

#### 관문2
우리 학과에 왜 지원했나요?

우리 학과에 진학하고 난 뒤의 진로 계획을 말씀해주세요.

우리 학과의 미래가 어떨 것 같나요?

#### 관문3
이 책에서 어떤 생각을 했나요? (책1) ~ 책(50)

#### 관문4
마지막으로 하고 싶은 말 있어요?

안 함.

임의의 조합을 만들어 순서대로 콘솔창에 출력하시오. 각 질문에 대해 키보드로 답변을 입력하도록 하시오.

example

	---모의면접 테스트를 시작합니다---
	자기소개 해보세요.
	-> 안녕^^
	우리 학과의 미래가 어떨 것 같나요?
	-> 밝아!
	이 책에서 어떤 생각을 했나요? (책46)
	-> 했어~
	안 함.
	---모의면접이 종료되었습니다---

단, 조건이 있습니다.

질문을 세 개 이상 해야 합니다!

자기소개도 안 하고, 마지막으로 하고 싶은 말도 안 하는 그런 꿀 같은 건 없다, 이 말입니다.


	import java.util.Random;
    import java.util.Scanner;
    
    public static void main(String[] args){
    	Random rand = new Random();
    	Scanner sc = new Scanner(System.in);
    
    	String[] question1 = {"자기소개 해보세요.", "안 함."};
    	String[] question2 = {"우리 학과에 왜 지원했나요?", "우리 학과에 진학하고 난 뒤의 진로 계획을 말씀해주세요.", "우리 학과의 미래가 어떨 것 같나요?"};
    	// String[] question3는 어떻게 해야 할까요?
    	String[] question4 = {"마지막으로 하고 싶은 말 있어요?", "안 함."};

		/*
    	
    	
    	*/
	}



## 2. 큰 수의 법칙
#### #java.util.Random #java.util.Scanner

난수에 관한 코드는 잘 짰는지 확인해보기가 쉽지 않다 ㅋㅋㅋ

java의 난수 생성기가 큰 수의 법칙을 따르는지 확인해보자.

실수형 원소를 갖는 리스트를 입력받아 양수의 비율을 반환한다.

	public static void main(String[] args){
    	Random rand = new Random();
    	List<Double> ranList = new ArrayList<Double>();
    	int n = 100;
    	for(int i=0; i<n; i++){
    		//여기에 적절한 코드를 쓰십시오.
        	}
	}
            
	public static double ratioOfPos(List<Double> list){
		/*
		*
		*
       	*/
    
    }


## 3. 자기소개서 글자수세기
#### #java.lang.String #java.util.Scanner

	public static void main(String[] args){
    	String essay = "저는 서울 불광동에서 1980년 3월에 2남 1녀의 막내로 태어났습니다. 공무원이셨던 아버님은 엄격함과 자상함으로 저희 형제들을 이끌어주셨으며, 어머님은 아버님의 완고함을 부드러움으로 보완하면서, 이어서 읽기.";
		countString(essay);
	}
    
    public static void countString(String essay){
    	/*
    	*
    	*/
    }



## 4. 수및연? 물실? 글기? 수강신청하자~
### 스누티티 교과목 검색 기능
#### #java.lang.String #java.util.Scanner


example

	---스누티티 시작---
	과목명을 입력하세요: 수및연2
    수학 및 연습2 033.002 정경훈 수리과학부
    과목명을 입력하세요: 데마
    데이터마이닝 406.429 조성준 산업공학과
    과목명을 입력하세요: 수및
    수학 및 연습2 033.002 정경훈 수리과학부
    과목명을 입력하세요: 수2
    수학 및 연습2 033.002 정경훈 수리과학부
    과목명을 입력하세요: 종료
    ---종료되었습니다---
    

dataset

	String[] subject1 = {"수학 및 연습2", "033.002 정경훈 수리과학부"};
    String[] subject2 = "데이터마이닝", "406.429 조성준 산업공학과"};
    String[] subject3 = "인간공학실험", "406.305A 윤명환 산업공학과"};

skeleton code

	public static void main(String[] args){
    	snutt();
	}
    
    public static void snutt(){
    	/*
    	*
    	*/
    }
