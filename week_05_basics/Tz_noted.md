## 📘 書籍資訊

本讀書會共筆內容是依據 **《為你自己學 Python（第二版）》** 所整理。  
作者：高見龍老師（[@kaochenlong](https://github.com/kaochenlong)）  
出版：旗標出版社，ISBN：9789863125641  
📖 書籍介紹頁面：[https://pythonbook.cc/](https://pythonbook.cc/)
讀書會排程: [study_plan.md](./study_plan.md)
> 本共筆為讀書會學習交流用途，內容皆為成員學習心得與練習，尊重原書著作權 🙏  
> 感謝一起學習的讀書會夥伴們
---

## 📚 Tz_notes

### 關於元組（Tuple）
1. 發音吐波或塔波都可以  
2. 是用()包起來  
3. 資料沒有規定都要相同類型  
4. 不可變的:不能新增、修改或移除裡面的元素，對新手而言本身就是好處  
5. 只有一個的時候:最後面要加上逗號，不然會被判定成字串  
6. 移除()也可以  
   (1)建議保留以維持可讀性  
   (2)【補充】只有一個又移除()還是要,才會判定為Tuple  
7. 可以透過索引值取得資料  
   (1)【補充】不可用索引值存取的都是無順序的資料類型
8. 因為不可變的特性，像是 `.append()`、`.insert()`、`.remove()` 這種修改 Tuple 的方法會Error
9. 如Tuple 內所有元素都是不可變的，則可以說這個 Tuple 完全是不可變的:可作為可雜湊物件，也可當字典的 Key  
10.  Tuple 的效能優於串列[List]  
    (1)因為不可變所以不需額外空間儲存變動資料  
    (2)可以透過內建的timeit計算執行一段程式碼所需要的時間  
    (3)與串列的抉擇考量:  
      a.要裝的資料是不會變動的，選 Tuple；有可能需要變動的，選串列(以容器分辨資料類型比較容易識別)  
      b.異質性（Heterogeneous）資料選Tuple；同質性（Homogeneous）資料選串列  
11.  複製的方式:  
    (1)使用 `tuple()`  
    (2)使用 copy 模組的 `copy()`函數  
    (3)使用切片  
12.  空的Tuple只有一種

### 關於集合（Set）
1. 集合裡的元素不會重複  
    (1)每個`nan`都是獨一無二的，不會因為重複被移除  
    (2)`None`是實際存在的值，用於表示沒有值  
3. 元素沒有順序  
4. 建立方式:  
   (1)用{}  
   (2)用set()>建空集合的話用這種  
5. 一種可迭代物件  
6. 新增元素使用集合的 `.add()`  
7. 刪除元素使用集合的 `.remove()`  
8. 刪除元素也可以用`.discard()`>但元素不存在的話不會報錯  
9. 清空集合裡的所有元素`.clear()`
10. 運算:  
    (1)交集（Intersection）:使用`&`或` .intersection()`  
    (2)聯集（Union）:使用`|`或`.union()`  
    (3)差集（Difference）:使用`-`或`.difference()`  
    (4)兩個集合完全沒有重疊的元素，使用`.isdisjoint()`會回傳Ture  

### 關於函數（Function）
1. 表示輸入值與輸出值間的關係  
    (1)【補充】函數可以沒有參數  
    (2)【補充】函數不一定要回傳值  
    (3)【補充】'return':這行執行完就不執行下一行了，回傳值可被儲存及使用(print的output不會被儲存)  
3. 參數（parameter）:輸入值  
4. 回傳值（return value）:回傳值  
5. 理想狀況是可以做到函數的輸出值只跟輸入值有關，沒有副作用的函數稱為純函數（Pure Function） 
6. 函數的命名最好能一眼看出功能，命名可參考函數式程式設計（Functional Programming）
7. 保留字不要用
8. 看不出用途的名稱不要用
9. `def():`在Python中定義函數的關鍵字，def後加函數名稱():  
    (1)引數（Argument）:`()`內放的是要帶進去的值  
    (2)定義函數的時候，放在小括號裡的是參數，在執行函數的時候，帶進小括號裡的是引數  
    (3)設定的參數數量要等於提供的引數數量，數量對不上會跳`arguments`  
11. Python透過縮排（Indentation）區分範圍（Scope）  
12. 本體可以放`pass`卡位，不能是空的，只有註解也算空的  
13. 呼叫函數:請求函數運行的動作或行為  
14. 執行函數:函數實際進行運算的過程  
15. 位置引數（Positional Argument）:需要按照順序、逐個傳入引數的方式  
    (1)`/`用於標記在這個位置前只使用位置引數    
16. 關鍵字引數（Keyword Argument）:直接指定參數的名稱，跟定義的參數位置不一樣也不影響計算  
    (1)跟位置引數可混用  
    (2)位置引數必須在關鍵字引數之前  
    (3)一個參數不能重複傳兩次  
    (4)`*`用於標記在這之後的參數只能使用關鍵字引數  
17. sorted()的定義:`sorted(iterable, /, *, key=None, reverse=False)  Return a new sorted list from the items in iterable.` >函數的第一個引數是位置引數，後面的 key 跟 reverse 是關鍵字引數  
18. 參數預設值:  
    (1)參數數量要跟規範一致，多或少都不行  
    (2)有設定預設值的話，有些參數可以不給  
    (3)有設定預設值的參數，要在沒有預設值的參數之後  
19. 不定數量參數: 在參數前加上`*`標記*以後的所有位置引數  

### 關於LEGB 規則
1. Python 的作用域:區域（Local, L）、封閉（Enclosing, E）、全域（Global, G）以及內建（Built-in, B）  
2. 區域（Local, L）:函數內  
3. 封閉（Enclosing, E）:如果函數內找不到，會往外一層找(到最外層都找不到就Error)  
4. 全域（Global, G）:函數外  
5. 內建（Built-in, B）:順位最低， Python 內建的函數或變數  

### 【補充】本週討論期間練習：
1.
```python
def func(*args, **kwargs): 
        print(args, kwargs)  
    func(1, 2, a=3, b=4)
```
> Output:`(1, 2) {'a': 3, 'b': 4}`
2. 
```python
x = 10
def mod():
    global x
    x = 20

mod()
print(x)
```
> Output:`20`
3.
```python
f = lambda x:x * 2
print(f(5))
```
> Output:`10`
4.
```python
a = 0
def hi():
    a = 10 # local variable

    def hey():
        global a # 全域
        a +=1
    hey()   # apply on global variable
    print(f"A - {a}") # this a is the local variable a

hi() #calculate global a to +1, thus a = 1 at this point
print(f"B - {a}") # print global a
```
> Output:`A - 10 B - 1`
5.
```python
def process_data(*args):
    s = set(args)
    return tuple(s)
print(process_data(1,2,2,3))
```
> Output:`(1, 2, 3)`
6.
```python
def modify(t, s):
    global x
    x = t[0]
    s.add(t[0])
    return s
x = 0
t = (1, 2, 3)
s = {4, 5}
print(modify(t, s), x) #內層已經跑完,x = 1
print(x, modify(t, s), x)
```
> Output:`{1, 4, 5} 1 ；1 {1, 4, 5} 1`
7.
```python
#補充練習
def cube_tuple(s):
    return tuple(x**3 for x in s)
print(cube_tuple({1, 2, 3}))
```
> Output:`(1, 8, 27)`
8.
```python
#補充練習
f = lambda t, s:s.difference(set(t)) #前面的是被減數，後面的是減數
print(f((1, 2, 3),{2, 3, 4, 5}))
```
> Output:`{4, 5}`

### 【補充】下週：
1.What's generator object?  
   -[Python 3.13.3 說明文件](https://docs.python.org/zh-tw/3.13/c-api/gen.html)  
   -[Generators in Python](https://www.geeksforgeeks.org/generators-in-python/)  
   -[產生器generator - Python 教學 - STEAM 教育學習網](https://steam.oxxostudio.tw/category/python/basic/generator.html)  
   
