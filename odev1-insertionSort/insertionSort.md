
patika.dev Veri Yapıları ve Algoritmalar 

## Insertion Sort Projesi

[22,27,16,2,18,6] -> Insertion Sort

1- Yukarı verilen dizinin sort türüne göre aşamalarını yazınız.

2- Big-O gösterimini yazınız.

3- Time Complexity: Average case: Aradığımız sayının ortada olması,Worst case: Aradığımız sayının sonda olması, Best case: Aradığımız sayının dizinin en başında olması.

4- Dizi sıralandıktan sonra 18 sayısı hangi case kapsamına girer? Yazınız.


[7,3,5,8,2,9,4,15,6] dizisinin Insertion Sort'a göre ilk 4 adımını yazınız.

## 1- **[22,27,16,2,18,6]** dizisinin sort türüne göre aşamaları:

```c
  for(i=1;i<size;i++)
  {
    j=i-1;
    while(j>=0 && arr[j]>arr[j+1])
    {
    	tmp=arr[j];
    	arr[j]=arr[j+1];
    	arr[j+1]=tmp;
    	j--;
	}
  }
```
1- Dizideki elemanlar arasında gezebilmek için bir `for` döngüsü açılır, sıralama yapabilmek için tanımlanmış `j` değişkeni `i-1` ifadesine eşitlenir.

2- `while` ile `j>=0` ve `arr[j]>arr[j+1]` şartları sağlandığı sürece dönecek bir döngü açılır. 

3- Şartlar sağlandığı zaman döngü içine girilir ve önceden tanımlanmış `tmp` değeri kullanılarak `arr[j]`ve `arr[j+1]`  değerleri arasında swap işlemi yapılır. Sıralamanın düzgün olması için geriye dönük bir kontrolün sağlanması adına `j` değeri bir azaltılır.

4- Şartlar sağlanmayana dek while döngüsü dönmeye devam eder. `while` döngüsünden çıkıldıktan sonra for döngüsüyle `i` değeri bir arttırılır. Buradaki döngünün de sona ermesiyle sıralama tamamlanmış olur.

**1. Döngü:** `i` değerinin 1'e eşitlenmesiyle başlayan döngü `j` değerinin 0 olmasıyla devam eder. `while` döngüsüne gelindiğinde `j>=0` şartı sağlanmasına rağmen `arr[0]>arr[1]` yani (22>27) şartı sağlanmadığı için döngüye girilmez. 

**2. Döngü:** `i` değeri bir arttırılıp 2'ye eşitlenir. Burada `j=1` olur. `while` döngüsüne gelindiğinde `j>=0` ve `arr[1]>arr[2]` ifadesi (27>16) doğru olduğundan `while` döngüsüne girilir. `arr[1]=27` ifadesi önce `tmp` değişkenine atanır, sonrasında `arr[2]=16` ifadesine eşitlenir; bunun ardından `arr[2]` ifadesinin `tmp`'ye eşitlenmesiyle swap işlemi tamamlanır. Bu durumda `arr[1]=16` ve `arr[2]=27` olmuş olur. `j` değeri bir azaltılarak `while` döngüsü için kontrol yapılır. Dizinin burdaki hali **[22,16,27,2,18,6]** olur.

`j>=0` (j=0) ve `arr[0]>arr[1]` ifadesi (22>16) doğru olduğundan bir kez daha `while` döngüsüne girilir. arr[0] ve arr[1] ifadeleri arasında bir swap işlemi daha gerçekleştirildiğinde arr[0]=16 ve arr[1]=22 olur. `j` değeri bir azaldığında `j>=0` şartını sağlamadığından `while` döngüsüne girilmez. 2. döngü tamamlanır.

Dizinin son hali **[16,22,27,2,18,6]** olur.

**3. Döngü:** `i=3` ve `j=2` olarak atanır. `arr[2]>arr[3]` ifadesinin (27>2) de doğru olmasıyla `while` döngüsünün şartları sağlanmış olur, döngüye girilir. `arr[2]` ve `arr[3]` ifadeleri arasında swap işlemi yapılır. `arr[2]=2` ve `arr[3]=27` olmuş olur. `j` değeri bir azaltılır. Dizinin buradaki hali **[16,22,2,27,18,6]** olur.

`while` döngüsünün şartları kontrol edilir. `j=1` ve `arr[1]>arr[2]` ifadesinin (22>2) doğru olmasıyla `while` döngüsü için şartlar sağlanmış olur. `arr[1]` ve `arr[2]` ifadeleri arasında swap işlemi yapılır. `arr[1]=2` ve `arr[2]=22` olur. `j` değeri bir azaltılarak `while` döngüsünün başına dönülür. Dizinin şimdiki hali **[16,2,22,27,18,6]** olur.

`j=0` ve `arr[0]>arr[1]` ifadesinin (16>2) doğru olmasıyla `while` döngüsünün şartları sağlanır. `arr[0]` ve `arr[1]` değerleri arasında swap işlemi gerçekleşir. `arr[0]=2` ve `arr[1]=16` olur. `j` değeri bir azaltıldığında `while` döngüsünün şartı sağlanmadığından 3. döngü tamamlanır. 

Dizinin son hali **[2,16,22,27,18,6]** olur.

**4. Döngü:** `i=4` ve `j=3` olarak atanır. `arr[3]>arr[4]` ifadesinin (27>18) olmasıyla `while` döngüsünün şartları sağlanır. `arr[3]` ve `arr[4]` ifadeleri arasında swap işlemi gerçekleştirilir. Böylelikle `arr[3]=18` ve `arr[4]=27` olur. `j` değeri bir azaltılır ve döngü devam eder. Dizinin buradaki hali **[2,16,22,18,27,6]** olur.

`arr[2]>arr[3]` şartı (22>18) sağlandığından yeniden döngüye girilir. swap işlemi yapıldıktan sonra `arr[2]=18` ve `arr[3]=22` olur. `j` değeri bir azaltılır.
`while` döngüsünün şartları kontrol edilirken `j>=0` şartı (j=1) sağlansa bile `arr[1]>arr[2]` (16>18) şartı sağlanmadığından `while` döngüsüne girilmez ve 4. döngü son bulur.

Dizinin son hali **[2,16,18,22,17,6]** olur. 

**5. Döngü:** `i=5` ve `j=4` olur. `while` döngüsü için `arr[4]>arr[5]` ifadesi (27>6) doğru olduğundan döngünün şartları sağlanmış olur. `arr[4]` ve `arr[5]` ifadeleri arasında swap işlemi yapılarak `arr[4]=6` ve `arr[5]=27` olarak eşitlenir. `j` değeri bir azaltılır. Dizinin yeni hali **[2,16,18,22,6,27]** olur.

`j=3` ve `arr[3]>arr[4]` ifadesi (22>6) doğru olduğundan dolayı `while` döngüsü çalışır. `arr[3]` ve `arr[4]` ifadeleri arasında swap işlemi yapılarak `arr[3]=6` ve `arr[4]=22` olarak atanır. `j` değeri bir azaltılır. Diziznin buradaki hali **[2,16,18,6,22,27]** olur.

`j=2` ve `arr[2]>arr[3]` ifadesi (18>6) doğru olduğundan `while` döngüsü çalışır. `arr[2]` ve `arr[3]` ifadeleri arasında swap işlemi yapılarak `arr[2]=6` ve `arr[3]=18` olarak eşitlenir. `j` değeri bir azaltılır. Dizinin yeni hali **[2,16,6,18,22,27]** olur.

`j=1` ve `arr[1]>arr[2]` ifadesi (16>6) doğru olduğundan `while` döngüsü çalışır. `arr[1]` ve `arr[2]` ifadeleri arasında swap işlemi yapılarak `arr[1]=6` ve `arr[2]=16` olaysk atanır. `j` değeri bir azaltılır. `j>=0` şartı (j=0) sağlanmasına  rağmen `arr[0]>arr[1]` şartı (2>6) sağlanmadığı için `while` döngüsüne girilmez.

`i` değeri de dizinin boyutundan `(size=6)` büyük olamayacağından dolayı `for` döngüsünden çıkılır. 

Dizinin son ve sıralanmış hali **[2,6,16,18,22,27]** olur.

## Big-O Notasyonu:

1-Average Case: `O(n²)`

2-Worse Case: `O(n²)`
**[27,22,18,16,6,2]** durumu worst case olarak kabul edilebilir.

3-Best Case: `O(n)` olur. **[2,6,16,18,22,27]** best case olarak kabul edilebilir. Dizi sıralı olduğundan for döngüsü tamamiyle sadece bir defa döner.

Time Complexity: 
Average case: Aradığımız sayının ortada olması, Worst case: Aradığımız sayının sonda olması, Best case: Aradığımız sayının dizinin en başında olması.
4- Dizi sıralandıktan sonra 18 sayısı `Average Case` kapsamına girer.


## [7,3,5,8,2,9,4,15,6] dizisinin Insertion Sort'a göre ilk 4 adımı: 


**1. Döngü:** `i` değerinin 1'e eşitlenmesiyle döngü başlar. `j=0` olur ve `while` döngüsünün şartları kontrol edilir. `j>=0` ve `arr[0]>arr[1]` ifadesi (7>3) doğru olduğundan `arr[0]` ve `arr[1]` ifadeleri arasında swap işlemi yapılır. `arr[0]=3` ve `arr[1]=7` olur. `j` değeri bir azaltılır. `j>=0` ifadesini sağlamadığından `while` döngüsüne girilmez ve 1. döngü tamamlanır. Dizinin buradaki hali **[3,7,5,8,2,9,4,15,6]** olur.

**2. Döngü:** `i=2` ve `j=1` olur. `arr[1]>arr[2]` ifadesi (7>5) doğru olduğundan `while` döngüsüne girilir. `arr[1]` ve `arr[2]` ifadeleri arasında swap işlemi yapılır. `arr[1]=5` ve `arr[2]=7` olur. `j` değeri bir azaltılır. Dizinin buradaki hali **[3,5,7,8,2,9,4,15,6]** olur.

`j=0` olmasına rağmen `arr[0]>arr[1]` ifadesi (3>5) sağlanmadığı için `while` döngüsüne girilmez ve 2. döngü son bulmuş olur.

**3. Döngü:** `i=3` ve `j=2` olur. `arr[2]>arr[3]` ifadesi (7>8) doğru olmadığından `while` döngüsüne girilmez ve 3. döngü son bulur.

**4. Döngü:**  `i=4` ve `j=3` olur. `arr[3]>arr[4]` ifadesi de (8>2) doğru olduğundan `while` döngüsü çalışır. `arr[3]` ve `arr[4]` ifadeleri arasında swap işlemi yapılarak `arr[3]=2` ve `arr[4]=8` olarak eşitlenir. `j` değeri bir azaltılır. Dizinin yeni hali **[3,5,7,2,8,9,4,15,16]** olur.

`j=2` ve `arr[2]>arr[3]` ifadesi (7>2) doğru olduğundan `while` döngüsü çalışır. `arr[2]` ve `arr[3]` ifadeleri arasında swap işlemi yapılarak `arr[2]=2` ve `arr[3]=7` olarak eşitlenir. `j` değeri bir azaltılır. Dizinin yeni hali **[3,5,2,7,8,9,4,15,16]** olur.

`j=1` ve `arr[1]>arr[2]` ifadesi (5>2) doğru olduğundan `while` döngüsü çalışır. `arr[1]` ve `arr[2]` ifadeleri arasında swap işlemi yapılarak `arr[1]=2` ve `arr[2]=5` olarak eşitlenir. `j` değeri bir azaltılır. Dizinin yeni hali **[3,2,5,7,8,9,4,15,16]** olur.

`j=0` ve `arr[0]>arr[1]` ifadesi (3>2) doğru olduğundan `while` döngüsü çalışır. `arr[0]` ve `arr[1]` ifadeleri arasında swap işlemi yapılarak `arr[0]=2` ve `arr[1]=3` olarak eşitlenir. `j` değeri bir azaltılır. `j=-1` olması durumunda `while` döngüsünün `j>=0` koşulu sağlanmayacağından döngüye girilmez. Böylelikle 4. döngü son bulur.

Dizinin son hali **[2,3,5,7,8,9,4,15,16]** olur.
