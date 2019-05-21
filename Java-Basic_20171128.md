Java Recursvie Function: Exercise
=============

## Tue, Nov 28th, 2017

## 재귀함수
### 자기 자신을 다시 호출해서 작업을 수행하는 함수


어느 한 컴퓨터공학과 학생이 유명한 교수님을 찾아가 물었다.
"재귀함수가 뭔가요?"
"잘 들어보게. 옛날옛날 한 산 꼭대기에 이세상 모든 지식을 통달한
선인이 있었어. 마을 사람들은 모두 그 선인에게 수많은 질문을 했고, 
모두 지혜롭게 대답해 주었지. 그의 답은 대부분 옳았다고 하네.
그런데 어느날, 그 선인에게 한 선비가 찾아와서 물었어.
"재귀함수가 뭔가요?"
"잘 들어보게. 옛날옛날 한 산 꼭대기에 이세상 모든 지식을...

### example.1
1*2*3*4*5*…*(n-1)*n 을 n!로 나타내며, 이를 피보나치 수열이라 부른다. n!을 구하는 메소드를 작성하시오.

solution.

	def fact(n):
   	 if ( n == 1):
   	     return 1
   	 return fact(n-1)*n


이를 점화식으로 표현하면 다음과 같다.

T(N) = N * T(N-1)
T(1) = 1


### example.2
$$\sum_{i=0}^n i$$

위 함수를 아래 코드를 완성하여 구현하시오.

	def sum(n):
   	 #여기 코드를 넣으세요.



### problem.1
아래 수열은 피보나치 수열이다. 피보나치 수열의 n번째 수를 구하는 메소드를 작성하시오.

	0 1 1 2 3 5 8 13 21 34 55 89 …


solution.

	public static void main(String[] args){
		int answer = fn(10); //n이 10일 때
		System.out.println(answer);
	}

	public static int fn(int n){
 		if(n==2){
        		return 1;
 		} else if(n==1){
    		return 0;
		}
		return fn(n-1) + fn(n-2);
	}


### problem.2
 2∗1의 직사각형 블럭을 이용하여 2∗n크기의 직사각형 모양으로 채우려고 한다. 그림은 아래와 같다. 가능한 방법의 수를 구하여라. 2∗1 직사각형 블럭은 무한정 있다고 가정한다. 이 때 숫자가 커질 수 있으므로 100,000,007 로 나눈 나머지를 출력하시오.
 
solution.
이 문제에 대한 점화식을 구하면, T(n) = T(n-1) + T(n-2) 이다. 피보나치 수열인 것이다.

	public static void main(String[] args){
		int answer = fn(10); //n이 10일 때
		System.out.println(answer);
	}

	public static int fn(int n){
		if(n==2){
			return 2;
		} else if(n==1){
			return 1;
		}
		return fn(n-1) + fn(n-2);
	}


## End of Document.