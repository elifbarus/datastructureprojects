# PROJE 1 Selection Sort

## Soru 1) [22,27,16,2,18,6] -> Insertion Sort

### a) Yukarı verilen dizinin sort türüne göre aşamalarını yazınız.

"|" işaretinin sol tarafı sıralı, sağ tarafı sıralanmamış kabul edilir. Soldan sağa ilerlenerek en küçük eleman dizinin başına, en küçük ikinci eleman, ilk elemanın sağına yerleştirilir.
Bu mantık dizideki elemanlar bitene kadar tekrarlanır ve dizi sıralı hale gelmiş olur.
1. adım ````[22|27,16,2,18,6]````22<27 olduğundan dizi aynı kaldı.
2. adım ````[22,27|16,2,18,6] --> [16,22,27,2,18,6]````  (16<27, 16 önce 27 elemanı ile yer değiştirdi. 16<22, daha sonra 22 elemanı ile yer değiştirdi. Dizi 3. elemana kadar sıralandı.)
3. adım ````[16,22,27|2,18,6] --> [2,16,22,27,18,6]````  (2<27, 2 önce 27 elemanı ile yer değiştirdi. 2<22, daha sonra 22 elemanı ile yer değiştirdi. 2<16, daha sonra 16 elemanı ile yer değiştirdi. Dizi 4. elemana kadar sıralandı.)
4. adım ````[2,16,22,27|18,6] --> [2,16,18,22,27,6]````  (18<27, 2 önce 27 elemanı ile yer değiştirdi. 18<22, daha sonra 22 elemanı ile yer değiştirdi. 18>16 olduğu için yer değiştirmedi. Dizi 5. elemana kadar sıralandı.)
5. adım ````[2,16,18,22,27,6] --> [2,6,16,18,22,27]````  (6<27, 6<22, 6<18, 6<16, 6<16 ve 6>2 olduğu için 2. eleman konumuna geldi. Dizi küçükten büyüğe sıralandı.
  
### b) Big-O gösterimini yazınız.

Big O notation algoritmanın performansını ya da time complexity(algoritmanın çalışması için gerekli süreyi) hesaplarken kullanılır. Algoritma çalışma süresi bulunduktan sonra, en yüksek dereceli terim big o notation olur.
Burada time complexity süresi zaman olarak değil işlem sayısı olarak ölçülür. Dolayısıyla bizim dizimizde tüm eleman sayısına n denirse, ilk sırada n, sonra n-1, daha sonra n-2... kadar işlem yapılacağı için 
n+(n-1)+(n-2)... işlemini hesaplamak için ````[n x (n+1)]/2```` formülü kullanılır. (n^2+n)/2 sonucunun en yüksek dereceli terimi n^2 dir. 
Bu sebeple big o notation ````O(n^2)```` olur.


### c) Time Complexity: Dizi sıralandıktan sonra 18 sayısı aşağıdaki case'lerden hangisinin kapsamına girer? Yazınız
18 sayısı dizinin ortasında olduğu için Average case.

## d) [7,3,5,8,2,9,4,15,6] dizisinin Selection Sort'a göre ilk 4 adımını yazınız.

Burada dizinin elemanları en küçük eleman sırayla yer değiştirir. Bu işleme ilk elemandan başlanır, yeri değişecek küçük elemanın yerine yer değiştirdiğimiz büyük sayı geçer. Dizi sıralanana kadar işlem tekrarlanır.
1. adım ````[7,3,5,8,2,9,4,15,6] --> [2,3,5,8,7,9,4,15,6]```` (2 elemanı artık sıralandı en başa geldi ona sonraki işlemlerde bakılmaz.)
2. adım ````[2,3,5,8,7,9,4,15,6] --> [2,3,5,8,7,9,4,15,6]```` (3 elemanı kalan elemanlar arasında en küçük bu sebeple yeri değişmez sıralanmış olur.)
3. adım ````[2,3,5,8,7,9,4,15,6] --> [2,3,4,8,7,9,5,15,6]````
4. adım ````[2,3,4,8,7,9,5,15,6] --> [2,3,4,5,7,9,8,15,6]````

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

# PROJE 2 Merge Sort

## Soru 2) [16,21,11,8,12,22] -> Merge Sort

### a)Yukarıdaki dizinin sort türüne göre aşamalarını yazınız.

Diziyi bir anda sıralamak yerine küçük parçalara ayırarak sıralarsak. Daha iyi performans kazancı sağlarız ve çalışma süresi kısalır.

#### 1. adım önce dizi ortadan bölünür, dizi tek sayılı elemana sahip ortadaki elemanı sola da sağa da konulabilir.
````
    [16,21,11,8,12,22]
      /           \
[16,21,11]   -  [8,12,22]
````
#### 2. adım dizi tekrar bölünür ben ortadaki elemanları sol diziye koymayı tercih ettim.
````
       [16,21,11,8,12,22]
          /            \
    [16,21,11]       [8,12,22]
    /       \          /     \
[16,21]    [11]     [8,12]   [22]
````
#### 3. adım elemanlar tek kalana kadar işlem tekrarlanacağı için bir kez daha bölünür.
````
         [16,21,11,8,12,22]
          /              \
      [16,21,11]        [8,12,22]
     /        \            /     \
 [16,21]     [11]       [8,12]   [22]
   /  \         \         /  \      \
[16] [21]     [11]     [8] [12]  [22]
````
#### 4. adım yeniden 2'li ve tekli dizi haline getirme:
````
16>21 --> [16,21] ve [11] sol parça,
8>12 --> [8,12] ve [22] sağ parça olur.
````
#### 5. adım yeniden 3'lü dizi haline getirme:
````
sol parça: 6>11>21 --> [6,11,21]
sağ parça: 8>12>22 --> [8,12,22]
````
#### 6. adım sağ ve sol parça önce büyükten küçüğe sıralanır ve tek dizi haline geri getirilmiş olur:

Soldaki elemanların en küçük olduğu biliniyor. Önce onlar karşılaştırılır ve sıralanır. 6<8. Sonra ortadaki elamanlar 11<12, en son sağdaki elemanlar karşılaştırılır 21<22 
Bir araya getirilir: ````[6,8,11,12,21,22]````



### b)Big-O gösterimini yazınız.
Bu yöntemde dizi eleman sayısına n denirse dizi 2'ye bölünerek daha sonra tek eleman kalana kadar 2'ye bölünür.
````

                     n
                   /    \
                n/2      n/2
               /   \      /  \
             n/2 - n/2  n/2 - n/2
````            
gibi bir formülasyon ortaya çıkar. Sürekli 2'ye bölünerek devam edeceği için 2^x=n olur 
````2^x=n --> x= logn olur.(2 tabanında)```` -->logn kere işlem yapılıyor demektir.
Birleştirme aşaması: Daha sonra, bu küçük parçalar, sıralanmış bir dizi oluşturmak üzere birleştirilir. Her bir birleştirme işlemi, en kötü durumda, her elemanın bir kez karşılaştırılmasını gerektirir, 
bu da birleştirme işleminin lineer zaman karmaşıklığına (n) sahip olacağı anlamına gelir.
Bu sebeple ````O(nlogn)```` olur. 

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

# PROJE 3 Binary Search Tree

## Soru 3) [7,5,1,8,3,6,0,9,4,2] ->Binary Search Tree

### [7,5,1,8,3,6,0,9,4,2] dizisinin Binary-Search-Tree aşamalarını yazınız.
Dizi çift eleman sayısına sahiptir bu sebeple ağacın bir tarafı daha fazla elemana sahip olacaktır. Binary Search Treede en üstte bulunan node Root olarak adlandırılır.
Root’tan küçük değere sahip olan node’lar Root’un sol tarafında yer alır, Root’tan büyük değere sahip olan node’lar Root’un sağ tarafında yer alır.
root x=7 olsun.
````
                      7
                    /   \
                   5     8
                 /  \      \
               1     6      9
             /  \
            0    3
                /  \
               2    4
````
1. adım 5<7, ağacın solunda yer alır.
2. adım 1<7 ve 1<5 ağacın solunda ve 5 rakamının sol dalında yer alır.
3. adım 8>7, ağacın sağında yer alır.
4. adım 3<7 ve 3<5, 3>1 olduğundan ağacın solunda 1 rakamının sağ dalında yer alır.
5. adım 6<7 ve 6>5 ağacın solunda 5 rakamının sağ dalında yer alır.
6. adım 0<7, 0<5, 0<1 olduğundan ağacın solunda 1 rakamının solunda yer alır.
7. adım 9>7 ve 9>8 ağacın sağında 8 rakamının sağ dalında yer alır.
8. adım 4<7, 4<5, 4>1, 4>3 olduğundan ağacın solunda 3 rakamının sağ dalında yer alır.
9. adım 2<7, 2<5, 2>1, 2<3 olduğundan ağacın solunda 3 rakamının sol dalında yer alır.













