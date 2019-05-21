Java Basic Classes
=============
Java SIG
---------
##### 참고 문헌: 서울대 산업공학과 정보경영 연구실, 교과목 컴퓨터의 개념 및 실습, 2017-1 강의자료, 허재석


# Object class
java.lang.Object
즉, java.lang package의 Object class입니다.

object class는 모든 class의 최상위 super class입니다.

## 주요 method

### int hashCode()

### String toString()
 객체를 문자열로 반환한다.
 toString()의 반환값은? className@객체의 hashCode
 각 class는 toString()을 Overrding하여 자신만의 문자열을 반환 가능하다.
 

	package dummy;
	class Dog {
    
    	String name;
        
		Dog(String name) {
		this.name = name;
		}
        
		@Override
		public String toString(){
        	return name;
        }
    }

	class mainMethod{
    
		public static void main(String[] args){
        	System.out.println(dog);
            Dog dog = new Dog("Joy");
			System.out.println(dog);
        }
    }
    
Console창

	dummy.Dog@2a139a55 (override 전)
	Joy (override 후)
   

### boolean equals(Object obj)
 - 객체의 reference 비교

	
    ==



 - 객체의 value 비교
 클래스의 작성자는 equals() method를 Overriding하여 사용하는 것을 원칙으로 한다.


	boolean equals(Object obj)
    
    


# Wrapper classes

# Math class

# Random class

	java.util.Random;
    Random ranNum = new Random();
    
    int nextBooelean() //true 또는 false를 각각 0.5의 확률로 반환
    int nextInt() //int형 난수를 고른 확률로 반환
    dobule nextInt(int n) //0이상 n미만의 int형 난수를 고른 확률로 반환
    double nextDouble() //0.0이상 1.0미만의 double형 난수를 고른 확률로 반환
    double nextGaussian() //표준정규분포를 따르는 난수 반환
    
    
java.util 패키지에 위치한다.
java.lang.Math.random() method보다 더 확장된 기능을 제공한다.

### 여기서 문제!
### nextBooelan(), nextInt(), nextDouble() method를 Math.random()을 이용하여 나타내시오.
Math.random()은 0.0이상 1.0미만의 double형 난수를 고른 확률로 반환한다.




# String class

	java.lang.String;
    //문자형 배열. 즉, char[]과 같다고 볼 수 있다.
    
    public final class String implements java.io.Serializable, Comparable {
    //...
    private char[] value;
	//...
	}

String class의 생성자
- String() 
- String(char[] value)
- String(String original)
- String(StringBuffer buffer)

	
    char[] data = {'a','b','c','d'};
    String str2 = new String(data);
    String str3 = new String("abcd");
    
    System.out.println(str2.equals(str3)); //true
    
    String 객체는 수정 불가능하다.
    즉, String 객체를 이용한 연산시마다 새로운 문자열을 가진 String 객체가 생성되어 메모리 공간을 차지한다.
    문자열간의 결합이나 추출 등 문자열을 다루는 작업이 많이 필요한 경우에는 String class 대신 StringBufferc lass를 사용하는 것이 좋다.
    
# 여기서 잠깐!
## API(Application Programming Interface)
운영체제나 프로그래밍 언어가 제공하는 유용한 기능을 제어할 수 있게 만든 인터페이스

Java API document
- 자바에서 제공하는 기본 class와 package를 포함하는 API를 설명하는 문서
- JDK 기본 class들의 field, method 등이 잘 정리되어 있다.
- https://docs.oracle.com/javase/9/docs/api/

# StringBuffer class

StringBuffer class의 생성자
- StringBuffer() 
- StringBuffer(String str)

문자열을 바로 입력하여 객체를 생성할 수 없다.
생성자를 이용해야 한다.
	
    //StringBuffer sb = "abcd"; 이거 안 된다.
    StringBuffer sb = new StringBuffer("abcd");
    StringBuffer sb = new StringBuffer();
    sb.append("abcd");

# 오늘의 DIY

문자열을 입력받아 문장과 문장 사이에 개행문자(\n)를 삽입하여 반환하는 메소드를 작성하시오.

	static String insertNewLines(String s){...}
    
    

문자열을 입력받아 문장과 문장 사이에 개행문자(\n)를 삽입하여 반환하는 메소드를 작성하시오.

	static String changeCases(String s){...}

        

주어지는 문자열은 아래와 같습니다.


	String input = "Java is a general-purpose computer programming language that is concurrent, class-based, object-oriented,[15] and specifically designed to have as few implementation dependencies as possible. It is intended to let application developers "write once, run anywhere" (WORA),[16] meaning that compiled Java code can run on all platforms that support Java without the need for recompilation.[17] Java applications are typically compiled to bytecode that can run on any Java virtual machine (JVM) regardless of computer architecture. As of 2016, Java is one of the most popular programming languages in use,[18][19][20][21] particularly for client-server web applications, with a reported 9 million developers.[22] Java was originally developed by James Gosling at Sun Microsystems (which has since been acquired by Oracle Corporation) and released in 1995 as a core component of Sun Microsystems' Java platform. The language derives much of its syntax from C and C++, but it has fewer low-level facilities than either of them.";
        
	String inserted = insertNewLines(input);
    String changed = changeCases(input);
    System.out.println(changed);