# 1์ฃผ์ฐจ - ๐งฑ ์คํ๊ณผ ํ

## [โ ๊ฐ์ ์ ๋ฆฌ]

### PART 01 ์คํ

#### ์คํ์ด๋? 
- ์์ด๋ก Stack '์๋ค' ๋ผ๋ ์๋ฏธ
- ํ๋ก๊ทธ๋๋ฐ์์ ๋ชฉ๋ก ํน์ ๋ฆฌ์คํธ์์ ์ ๊ทผ์ด ํ์ชฝ์์๋ง ๊ฐ๋ฅํ ๊ตฌ์กฐ
- LIFO(Last-In, First-Out)๊ฐ ๊ธฐ๋ณธ์๋ฆฌ
- ๋ํ์ ์ธ ๋ด์ฅํจ์
	- push
	- peek
	- pop
<br/>

#### ์คํ์ ๊ตฌ์กฐ
BOOKS
[ BOOK 1, BOOK 2, BOOK 3]

- push : ๊ฐ์ฅ ๋ง์ง๋ง์ ์ถ๊ฐ
push BOOK 4 -> BOOKS [ BOOK 1, BOOK 2, BOOK 3, BOOK 4 ]

- peek : ๊ฐ์ฅ ๋ง์ง๋ง ๋ฐ์ดํฐ ํ์ธ
peek BOOKS -> BOOK 4

- pop : ์ ์ผ ๋ง์ง๋ง ๋ฐ์ดํฐ ์ถ์ถ
pop BOOKS -> BOOKS [ BOOK 1, BOOK 2, BOOK 3]
<br/>

#### PYTHON ์คํ์ ๊ตฌํ ๋ฐฉ๋ฒ
- ์ง์  ๊ตฌํ
- ์ด๋ฏธ ๊ตฌํ๋ ํด๋์ค import
- List๋ฅผ ์คํ์ผ๋ก ๊ตฌํ

- ์คํ์์ '์ด๋ฏธ ๊ตฌํ๋ ํด๋์ค import', 'List๋ฅผ ์คํ์ผ๋ก ๊ตฌํ' ์์
<br/>

#### PYTHON ์คํ ์ง์  ๊ตฌํ ๋ฐ ํ์ฉ
```python
class Stack(list) :
	push = list.append
	
	def peek(self) :
		return self[-1]
			self[len(self)-1]

# Pop์ list์ ๋ด์ฅํจ์๋ก ์ด๋ฏธ ์กด์ฌํ๋ค.

s = Stack()
s.push(1)
s.push(5)
s.push(10)

print("my stack is : ", s)			my stack is :  [1, 5, 10]
print("popped value is : ", s.pop())	popped value is :  10
print("my stack is : ", s)			my stack is :  [1, 5]
print("peeked value is : ", s.peek())	peeked value is :  5
print("my stack is : ", s)			my stack is :  [1, 5]
```
<br/>

#### PYTHON List๋ฅผ ์คํ์ผ๋ก ํ์ฉ
```python
s = []
s.append(1)
s.append(5)
s.append(10)
print("my stack is : ", s)			my stack is :  [1, 5, 10]
print("poped value is : ", s.pop())	poped value is :  10
print("my stack is : ", s)			my stack is :  [1, 5]
print("peeked value is : ", s[-1])		print("peeked value is : ", s[-1])
print("my stack is : ", s)			print("my stack is : ", s)
```
<br/>

#### ์คํ์ ํ์ฉ
- ์นํ์ด์ง์์ ์ด์ ํ์ด์ง ๋ค์ํ์ด์ง ๊ธฐ๋ฅ
- ๊น์ด ์ฐ์  ํ์(DFS)
<br/>


### PART 02 ํ

#### ํ๋?
- ์์ด๋ก Queue '์ผ์ด ์ฒ๋ฆฌ๋๊ธฐ๋ฅผ ๊ธฐ๋ค๋ฆฌ๋ ๋ฆฌ์คํธ' ๋ผ๋ ์๋ฏธ
- ํ๋ก๊ทธ๋๋ฐ์์ ๋ชฉ๋ก ํน์ ๋ฆฌ์คํธ์์ ์ ๊ทผ์ด ์์ชฝ์์ ๊ฐ๋ฅํ ๊ตฌ์กฐ
- FIFO(First-In, First-Out)๊ฐ ๊ธฐ๋ณธ์๋ฆฌ
- ๋ํ์ ์ธ ๋ด์ฅํจ์
	- put
	- peek
	- get
<br/>

#### ํ์ ๊ตฌ์กฐ
BOX ๋ฆฌ์คํธ
[ BOX 1, BOX 2, BOX 3]

- put : ๊ฐ์ฅ ๋ง์ง๋ง์ ์ถ๊ฐ
put BOX 4 -> BOX ๋ฆฌ์คํธ [ BOX 1, BOX 2, BOX 3, BOX 4 ]

- peek : ๊ฐ์ฅ ๋จผ์  ๋ค์ด๊ฐ ๋ฐ์ดํฐ ํ์ธ
peek BOX ๋ฆฌ์คํธ -> BOX 1

- pop : ์ ์ผ ๋ง์ง๋ง ๋ฐ์ดํฐ ์ถ์ถ
get BOX ๋ฆฌ์คํธ -> BOX ๋ฆฌ์คํธ [ BOX 2, BOX 3, BOX 4 ]
<br/>
		
#### PYTHON ํ์ ๊ตฌํ๋ฐฉ๋ฒ
- ์ง์  ๊ตฌํ
- ์ด๋ฏธ ๊ตฌํ๋ ํด๋์ค import
- List๋ฅผ ํ๋ก ๊ตฌํ
<br/>

#### PYTHON ํ ์ง์  ๊ตฌํ ๋ฐ ํ์ฉ
```python
class Queue(list) :
    put = list.append
    
    def peek(self) :
        return self[0]
    
    def get(self):
        return self.pop(0)

q = Queue()
q.put(1)
q.put(5)
q.put(10)

print("my queue is : ", q)			my queue is :  [1, 5, 10]
print("removed value is : ", q.get())	removed value is :  1
print("my queue is : ", q)			my queue is :  [5, 10]
print("peeked value is : ", q.peek())	peeked value is :  5
print("my queue is : ", q)			my queue is :  [5, 10]
```
<br/>

#### PYTHON ๊ตฌํ๋ ํด๋์ค import
* ๊ฐ์ ์ค๋ฅ์ธ๋ฏ ํ๋ค... ์๋จ....
```python
from queue import Queue

q = Queue()
q.put(1)
q.put(5)
q.put(10)

print("my queue is : ", q)
print("removed value is : ", q.get())
print("my queue is : ", q)
print("peeked value is : ", q.peek())
print("my queue is : ", q)
```
<br/>

#### PYTHON List๋ฅผ ํ๋ก ํ์ฉ
```python
q = []
q.append(1)
q.append(5)
q.append(10)

print("my queue is : ", q)			my queue is :  [1, 5, 10]
print("removed value is : ", q.pop(0))	removed value is :  1
print("my queue is : ", q)			my queue is :  [5, 10]
print("peeked value is : ", q[0])		peeked value is :  5
print("my queue is : ", q)			my queue is :  [5, 10]
```
<br/>

#### ํ์ ํ์ฉ
- ํ๋ฆฐํฐ ์ธ์ ๋๊ธฐ์ด
- ๋๋น ์ฐ์  ํ์(BFS)

<br/><br/>

## [๐ฅ ๋ฌธ์ ํ์ด]

### W01_1_์ฃผ์๊ฐ๊ฒฉ
- [๋ฌธ์  ์๋ณธ ๋ณด๊ธฐ](https://programmers.co.kr/learn/courses/30/lessons/42584)
- [ํ์ด ๋ณด๊ธฐ](./../code/practice/prc_w01_1_์ฃผ์๊ฐ๊ฒฉ.py)

<br/>

### W01_2_๊ธฐ๋ฅ๊ฐ๋ฐ
- [๋ฌธ์  ์๋ณธ ๋ณด๊ธฐ](https://programmers.co.kr/learn/courses/30/lessons/42586)
- [ํ์ด ๋ณด๊ธฐ](./../code/practice/prc_w01_2_๊ธฐ๋ฅ๊ฐ๋ฐ.py)

<br/>

### W01_3_๋ค๋ฆฌ๋ฅผ ์ง๋๋ ํธ๋ญ
- [๋ฌธ์  ์๋ณธ ๋ณด๊ธฐ](https://programmers.co.kr/learn/courses/30/lessons/42583)
- [ํ์ด ๋ณด๊ธฐ](./../code/practice/prc_w01_3_๋ค๋ฆฌ๋ฅผ์ง๋๋ํธ๋ญ.py)

