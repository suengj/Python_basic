**본 내용은 코딩책과 함께보는 코딩개념 사전 (김현정 저, 궁리출판사)의 11장 부분을 참고하고 있음을 알립니다**

[TOC]

#### 클래스와 객체
##### 클래스와 객체의 의미
1. 객체(Object)는 개별화된 무언가
2. 클래스(Class)는 유사한 객체들을 종류별로 모아놓은 일종의 부류; 보다 일반화된 형태

##### 클래스 정의(Class Definition)
클래스라는 키워드 뒤에 이름을 지어준 뒤, 객체의 속성과 행동을 변수와 메소드로 정의를 하면 된다.

```python
# class에 대한 이름을 정의한다. 
# 이하 항목은 bicycle Class를 구성하는 멤버 변수이다.
class bicycle: 	  
	color='yellow'
	wheel=2
	speed='normal'
	gear=3

	# 메소드를 정의하는 부분 - Speed와 Gear의 변수를 변경한다.
	def changeSpeed(self,s):	 
		print('changeSpeed 호출')
		self.speed=s
		
	def changeGear(self,n):
		print('changeGear 호출')
		self.gear = n
		
# 메소드의 변경이 발생할 때, self는 메소드 내부의 멤버 변수를 활용한다는 것을 의미한다. 
```

##### 클래스와 객체
이러한 클래스를 정의하는 것은 향후 다양한 종류의 변수를 만들어내기 위한 기본적인 도면과 같은 역할을 한다. 따라서 이러한 클래스가 정의된 이후에 해당 클래스의 속성을 갖게 되는 다양한 변수를 만들 수 있다.

클래스에는 속성(멤버 변수)과 메소드가 정의가 되고, 객체는 클래스의 특징을 구현하기 때문에 객체 간에는 실질적으로 구현된 속성과 메소드 간에 차이가 있을 수 있다. (본질은 같으나 구체적인 부분이 다르다는 것)

```python
# 앞서 활용한 클래스를 동일하게 적용한다고 가정하고,

myBicycle1=bicycle()
myBicycle2=bicycle()
```
이라고 작성을 할 경우, bicycle의 클래스를 받게 되는 두 가지 객체를 만들 수 있다. 이제 bicycle의 변수 값들을 조정하여 myBicycle들을 각기 다른 속성을 가진 객체로 만들 수 있다. 

```python
myBicycle1.gear = 1
myBicycle2.gear = 2
```
라고 정의를 할 경우, 기존 bicycle Class에 정의가 되어 있는 gear의 값이 해당 객체 내에서 조정된다는 것을 알 수 있다. 

```python
# 객체 멤버 변수의 할당 값을 확인하고자 할 때
# 객체.변수로 입력하면 된다. 
myBicycle=bicycle()
myBicycle.color
```
라고 입력을 하게 된다면, myBicycle이라는 객체에 할당된 클래스에 정의된 color라는 멤버 변수 값을 확인 할 수 있다. (즉, 데이터 타입이 무엇인지 먼저 확인한 뒤에 해당 변수의 할당 값을 변경 할 수도 있다)

정리하자면,

**<자전거 - 클래스>**: 속성(멤버 변수)에는 color, wheel, speed, gear가 있고, 메소드에는 speed와 gear를 조정 할 수 있다. (일종의 행동을 의미)

| 자전거(객체) | mybicycle1 | mybicycle2 | mybicycle3 |
|-------|----------|----------|----------|
|속성(color)|빨간색|파란색|노란색|
|메소드(Speed)|changeHigh|changeLow|changeStop|

이런 식으로 이해를 할 수 있다. 


##### 객체 메소드
```python
class bicycle: 	  
	color='yellow'
	wheel=2
	speed='normal'
	gear=3

	def changeSpeed(self,s):	 
		print('changeSpeed 호출')
		self.speed=s
		
	def changeGear(self,n):
		print('changeGear 호출')
		self.gear = n
		 
```

잠시, 클래스가 정의된 bicycle을 돌아와서 살펴보면, 객체의 메소드를 변경함으로써 객체의 멤버 변수를 바꿀 수 있다. 

먼저 메소드 부분을 살펴보면, changeSpeed(self,s): 부분이 존재하는데, 이 부분은 클래스에 정의된 함수로써, changeSpeed라는 함수를 통하여 메소드 내 할당된 멤버 변수 값 혹은 기타 내용들을 수행 할 수 있다. 또한 이들 changeSpeed함수의 경우에는 참조하는 변수가 self이기 때문에 별도로 class에 대한 언급을 하지 않아도 된다. 

`myBicycle.changeSpeed('high')` 라고 입력을 할 경우, 해당 def에 의하여 self.speeds 즉, bicycle의 클래스 내부에 있는 speed 변수를 변경하게 된다. 즉, 현재 코드로만 본다면`myBicycle.speed = 'high'`라고 쓰는 것과 차이는 없지만, 클래스 내에 정의된 함수가 보다 복잡하거나 할 경우, 활용을 할 수 있다. 

##### 객체 생성자(Constructor)
객체를 만드는 시점에 초기화된 값을 호출하기 위해서 작성하는 것이다. 코드의 예제는 다음과 같다. 

```python
class bicycle: 	  
	color='yellow'
	wheel=2
	speed='normal'
	gear=3

	# 아래 코드는 객체 생성자 (__init__)이다. 
	def __init__(self,c,n):
		self.color = c
		self.gear = n

	def changeSpeed(self,s):	 
		print('changeSpeed 호출')
		self.speed=s
		
	def changeGear(self,n):
		print('changeGear 호출')
		self.gear = n
		 
```

다시 말하여 bicycle이라는 클래스를 활용하여 객체를 설정할 때, color와 gear에 대한 언급을 해주어야 해당 객체의 초기값을 실현 할 수 있다. 

`myBicycle=bycicle('black',2)`라고 적어야, myBicycle이라는 객체를 형성 할 때, black -> self.color = 'black' -> color=black / 2 -> self.gear -> gear =2 이 가능해지는 것이다. 
만약에 객체 생성자가 있음에도 불구하고 이에 대한 언급이 없이 객체를 만들 경우 오류가 반환된다. 

##### 상속(Inheritance)
상위 클래스(부모 클래스)의 속성을 하위 클래스(자식 클래스)가 물려 받는다는 개념을 뜻한다. 

`class childBicycle(bicycle)`이라고 작성을 하며, childBicycle이라는 클래스를 작성하기 시작할 경우, bicycle의 클래스 속성 값이 모조리 childBicycle에 넘어 올 수 있다. 이에 따라서 childBycicle 클래스는 부모 클래스의 멤버 변수와 메소드를 사용 할 수 있다. 

예컨대, 
```python
childMyBicycle1 = childBicycle()
childMyBicycle1.changeSpeed('high')
```
이라고 작성을 할 경우, childMyBicycle은 그 자체로 클래스에 speed에 대한 함수가 정의되어 있지 않음에도 불구하고, 부모 클래스에 있는 함수 값을 물려 받아 속도를 변경 할 수 있는 것이다.

###### 내 생각
***따라서 클래스의 개념은 보다 추상적인 것이고 이후 자식 클래스 등으로 내려올 때마다 상속을 해줄 수 있기 때문에 보다 구체화된 클래스를 설정 할 수 있다고 볼 수 있다.***
*** 이후 개별 클래스를 통해서 실질적으로 수행가능한 객체들을 만들어 낼 수 있기 때문에 더욱 구체적인 내용을 수행 할 수 있다***

물론 자식 클래스에도 별도의 메소드를 정의하여 활용 할 수 있다. 

***결국 체계적으로 코드를 작성하기 위해서는 어떠한 개념으로 클래스가 정의되고 구조화 되어 있는지를 직관적으로 이해 할 수 있게끔 만들어야 한다***

```python
class childBicycle(bicycle):
	def changeColor(self,c):
		print('changeColor 호출')
		super.color = c
```
라고 작성을 하게 될 경우 childBicycle 내에서 color를 변경하는 호출을 하게 되면, 해당 값이 super(부모 클래스)에 넘어가게 되어 해당 color에 대한 호출을 불러올 수 있다. 

##### 오버로딩(Overloading)
파이썬의 경우 동일한 이름의 메소드이지만, 인자 개수가 다를 경우 서로 다른 메소드이다. 따라서 오버로딩의 경우 다양한 메소드를 처리 할 수 있게끔 처리를 할 수 있다.

```python
def changeColor(self, c=None)
	if c is not None:
		print('자전거 색깔:' +c)
	else:
		print('자전거 색깔: yellow')
```
라는 구문의 예시를 든다면, changeColor라는 함수에 c=None이라는 표시를 함으로써 인자가 있거나 없음을 나타내고, 이러한 두 가지 경우에 대하여 각기 다른 자전거 색깔을 print하도록 설정을 할 수 있다. 즉, changeColor이지만 인자의 개수에 따라 두 가지 형태의 메소드를 출력 할 수 있게 설정을 할 수 있다. 


##### 오버라이딩(Overriding)
부모/자식의 클래스가 있을 경우, 동일한 메소드가 있을지라도 부모 클래스 내의 메소드 보다 자식 클래스에 있는 메소드에 우선권이 할당된다는 개념이다. 

이럴 경우, 동일한 메소드명일지라도 수행하는 방식이 다르다면 수행되는 클래스에 가까운 메소드가 실행된다는 의미일 것이다. 

###### 내 생각
***어떻게 본다면 오버라이딩의 개념은 global, local 변수와 유사할지도 모른다는 생각이 들었다***

##### 클래스 변수(Class Variable)와 인스턴스 변수(Instance Variable)

객체들이 사용하는 변수: 인스턴스 변수
객체들이 모두 공유하는 변수: 클래스 변수

```python
class bicycle:
	numOfObject = 0
	
		def __init__(self,color,speed,gear):
			self.color = color
			self.speed = speed
			self.gear = gear
			bicycle.numOfObject += 1
			
		def changeSpeed(self,speed):
		self.speed = speed
		
		def changeGear(self,gear):
		self.gear = gear
			
mybicycle1 = bicycle(color,speed,gear)
mybicycle2 = bicycle(color,speed,gear)
```

라고 하게 될 경우, 두 종류의 객체를 형성하였다. 이때 bicycle이라는 클래스에서 numOfObject는 모든 객체가 사용 하고 있는 클래스 수준의 변수이지만, color, speed, gear의 경우는 클래스에서 정의는 되지만, 객체마다 서로 다르게 사용되는 변수를 의미하기 때문에 인스턴스 변수이다. 

mybicycle1을 실행하게 되면, numOfObject가 +1이 되어 class 자체 수준에서 변화를 하게 된다. mybicycle2를 실행하게 될 경우, color, speed, gear는 초기화되지만 다시 bicycle.numOfObject는 기존의 numOfObject에 1이 추가되어 2가 반환이 된다. 

이후 def changeSpeed와 changeGear에 의하여 bicycle 클래스에서 메소드가 정의되었기 때문에 각각의 객체는 클래스에서 활용 할 수 있는 메소드를 사용 할 수 있다. 

\* 인스턴스 변수의 경우에는 self.~~를 붙여주어야 한다. 만약 self가 없이 color, speed, gear 등으로 적는다면 이들은 def 내부에서만 활용되는 local 변수로 인식이 되기 때문에 self. 즉, bicycle 내부에서 활용된다고 인식이 되지 않아 오류가 발생한다. 