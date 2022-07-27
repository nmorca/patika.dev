patika.dev Veri Yapıları ve Algoritmalar

# Merge Sort Projesi

[16,21,11,8,12,22] -> Merge Sort

1- Yukarıdaki dizinin sort türüne göre aşamalarını yazınız.

2- Big-O gösterimini yazınız.

# [16,21,11,8,12,22] Dizisinin Merge Sort'a göre aşamaları:

              [16,21,11,8,12,22]
         
          [16,21,11]      [8,12,22]
      
      [16,21]   [11]       [8,12]   [22]
   
    [16]   [21]   [11]    [8]  [12]  [22]
     
      [16,21]   [11]       [8,12]   [22]
        
          [11,16,21]      [8,12,22]
             
              [8,11,12,16,21,22]

# Big-O Notasyonu:

Merge sort algoritması best, worst ve average case'de de `O(nlogn)` olarak çalışır.






