## Quick Sort Algorithm은 무엇인가요?
Quick Sort 알고리즘은 말 그대로 매우 빠른 정렬 수행 능력을 보여주는 알고리즘 입니다. Quick Sort Algorithm(이하 퀵 소트 알고리즘)은 다른 비교 정렬 알고리즘과 마찬가지로 하나의 기준 원소와 다른 원소와의 비교를 통해 작은 값부터 큰값으로 혹은 큰 값부터 작은 값으로 오름차순 및 내림차순 정렬을 하는 것이 목적인 알고리즘 입니다.



다른 값과 비교연산을 수행하는 기준 원소는 'Pivot' 이라고 불립니다. 이 pivot 값을 통해 진행되는 퀵소트 알고리즘의 정렬 과정을 간단하게 설명하자면 정렬을 수행해야하는 데이터의 값들 중에서 Pivot이 되는 값을 설정한 후 pivot 자기 자신을 제외한 나머지 원소들과 비교를 진행합니다. 오름차순 정렬을 진행한다는 가정 하에 비교하는 원소가 pivot 값보다 작다면 pivot 앞쪽에 위치하도록 설정하고 크다면 pivot 뒤쪽에 위치하도록 값의 위치를 변경합니다.

<img src="https://github.com/bnbong/Myblog_posts/blob/master/posts/Study/20201228132415/img.gif?raw=true" width="100%" height="30%" title="QSA" alt="QSA"></img>
<!-- ![QSA](https://github.com/bnbong/Myblog_posts/blob/master/posts/Study/20201228132415/img.gif?raw=true) -->
 > Quick Sort Algorithm 수행 모습 - 출처 : wikipedia
   
오름차순 퀵소트 알고리즘을 수행하게 되면 결국 피벗 앞에는 피벗보다 작은 원소들이 오게 되고 피벗 뒤에는 피벗 보다 큰 원소들이 위치하게 됩니다. 피벗을 기준으로 데이터들의 리스트를 둘로 분할하여 해당 퀵소트를 재귀적으로 반복하여 분할된 리스트의 크기가 0이나 1이 되면 알고리즘 수행이 종료됩니다.


<img src="https://github.com/bnbong/Myblog_posts/blob/master/posts/Study/20201228132415/dividing_pivot.png?raw=true" width="100%" height="30%" title="dividing_pivot" alt="dividing_pivot"></img>
<!-- ![dividing_pivot](https://github.com/bnbong/Myblog_posts/blob/master/posts/Study/20201228132415/dividing_pivot.png?raw=true) -->
 > 피벗 값을 기준으로 리스트를 둘로 쪼개는 모습
   
해당 알고리즘을 C++기반의 알고리즘 언어로 표현하게 되면 다음과 같습니다. 하단에 작성된 알고리즘은 C++ 기반으로 작성이 되었으나, 단순히 알고리즘을 표현하기 위해 세부 문법을 고려하지 않고 작성하였기 때문에 문법적인 오류가 존재할 수 있습니다.
   
```
void quicksort (index low, index high){ // low for first index, high for last index.   
	index pivotpoint;   
    if ( high > low) {   
    	partition( low, high, pivotpoint);   
        quicksort( low, pivotpoint - 1);   
        quicksort( pivotpoint + 1, high);   
    }   
}
```
   
```
void partition (index low, index high, index& pivotpoint) { // partition two lists
	index i,j;
    keytype pivotitem;
    pivotitem = S[low]; // Choose first item for pivotitem
    j = low;
    for( i = low + 1; i <= high; i++) {
    	if( S[i] < pivotitem) {
        	j++;
            exchange S[i] and S[j];
        }
        pivotpoint = j;
        exchange S[low] and S[pivotpoint]; // Put pivotitem at pivotpoint
    }   
}
```
   
정렬을 수행하는 리스트의 첫 번째 원소를 S[0]이 아니라 S[1]이라고 가정을 해두고 partition 함수를 처음으로 수행하면 다음과 같은 결과가 나오게 됩니다.

<img src="https://github.com/bnbong/Myblog_posts/blob/master/posts/Study/20201228132415/partition_result.png?raw=true" width="100%" height="30%" title="partition_result" alt="partition_result"></img>
<!-- ![partition_result](https://github.com/bnbong/Myblog_posts/blob/master/posts/Study/20201228132415/partition_result.png?raw=true) -->
 > partition 함수의 수행 결과
   
여기서, 해당 알고리즘은 pivot을 리스트의 첫 번째 값으로 설정하고 퀵소트 알고리즘을 수행했습니다. partition함수의 수행 로그를 따라가 보면 S[1]에 저장된 원소인 15가 pivot값으로 설정이 되었고 리스트의 인덱스의 위치를 가리키는 i와 j의 값에 변화를 주면서 S[i]와 S[j] 값을 비교하여 자리바꿈을 진행하면서 pivot보다 큰 값과 작은 값을 분류하는 작업을 합니다. 



partition함수의 시간복잡도는 첫 번째 원소를 제외한 나머지 원소들 끼리의 비교를 진행하므로 전체적인 데이터의 크기(input size)를 n 이라고 설정을 했을 때, 시간 복잡도는 다음과 같은 값을 갖게 됩니다.



__*T(n) = n - 1*__



퀵소트 알고리즘을 사용하여 n개의 원소의 개수를 가지는 리스트를 정렬하는데 걸리는 시간을 T(n)이라고 할 때 시간 복잡도 T(n)의 값은 다음과 같은 풀이과정을 통해 얻을 수 있습니다.

<img src="https://github.com/bnbong/Myblog_posts/blob/master/posts/Study/20201228132415/QSA_time_complexity.png?raw=true" width="100%" height="30%" title="QSA_time_complexity" alt="QSA_time_complexity"></img>
<!-- ![QSA_time_complexity](https://github.com/bnbong/Myblog_posts/blob/master/posts/Study/20201228132415/QSA_time_complexity.png?raw=true) -->
 > Quick Sort Algorithm의 평균 time complexity
   
평균적으로 퀵소트 알고리즘은 nlog2n이라는 시간 복잡도를 얻게 됩니다. worst case의 경우는 pivot 값을 정렬을 수행하는 리스트의 최솟값 혹은 최댓값으로 설정할 때 발생하게 됩니다. 최솟값 혹은 최댓값이 pivot으로 설정되었을 경우, 퀵소트 알고리즘을 수행하면 pivot값을 기준으로 분할되는 리스트는 항상 한쪽은 0개, 한쪽은 n-1개로 분할이 되게 됩니다. 이 경우 n-1개로 분할된 리스트는 n-1번 비교연산을 진행하고 이 과정을 총 n번 반복하게 되므로 최악의 time complexity가 도출되게 됩니다.


<img src="https://github.com/bnbong/Myblog_posts/blob/master/posts/Study/20201228132415/QSA_worst_time_complexity.png?raw=true" width="100%" height="30%" title="QSA_worst_time_complexity" alt="QSA_worst_time_complexity"></img>
<!-- ![QSA_worst_time_complexity](https://github.com/bnbong/Myblog_posts/blob/master/posts/Study/20201228132415/QSA_worst_time_complexity.png?raw=true) -->
 > Quick Sort Algorithm의 worst-case time complexity
   
이를 통해 quick sort algorithm을 사용할 때는 pivot값을 어느 값으로 설정하냐에 따라 매우 효율적인 알고리즘이 될 수도, 매우 비효율적인 알고리즘이 될 수도 있습니다. 따라서 빠르고 안정적인 수행 시간을 얻기 위해서는 pivot값 설정 전략에 대한 고민이 필요합니다.





## Quick Sort 알고리즘 실험


### **실험 준비**
효율적으로 quick sort 알고리즘을 사용하기 위해서는 데이터의 어떤 값이 pivot값으로 설정 되어야 하는지 각기 다른 pivot 선택 방식을 가지는 quick sort 알고리즘을 Python 언어로 구현해 실험을 해보았습니다.



오름차순으로 정렬을 수행한다고 가정하여 상단에 소개한 C++기반의 psudo로 작성된 partition 함수와 quicksort 함수를 구현한 코드는 다음과 같습니다.
   
```
import time

# 이하 코드는 pivot 값을 맨 첫번째 값으로 정했을 때의 퀵정렬 알고리즘 이다.
def partition_ASC(arr, start, end, comp, exchange): # 오름차순으로 분배
    pivot = arr[start]
    L = start
    R = end
    done = False

    while not done:

        while L <= len(arr)-1 and arr[L] <= pivot: # comparison
            if L == len(arr)-1:
                break
            comp += 1
            L += 1

        while R >= 0 and pivot < arr[R]: # comparison
            if R == 0:
                break
            comp += 1
            R -= 1

        if R <= L:
            done = True

        else: # low < high -> swap
            exchange += 1
            arr[L], arr[R] = arr[R], arr[L]

    # change pivot and high -> swap
    exchange += 1
    arr[start], arr[R] = arr[R], arr[start]

    return R, comp, exchange


def quick_sort_ASC(arr, start, end, comp, exchange): # 오름차순으로 정렬
    if start < end:
        pivot, comp, exchange = partition_ASC(arr, start, end, comp, exchange)
        quick_sort_ASC(arr, start, pivot - 1, comp ,exchange)
        quick_sort_ASC(arr, pivot + 1, end, comp, exchange)
    return arr, comp, exchange
```
   
해당 quick sort 소스코드의 수행 능력을 분석하기 위해 비교연산 횟수와 원소 간의 위치 교환이 발생되는 횟수, input size (n)의 크기 별로 어느정도의 수행 시간이 걸리는지 ms단위로 측정을 진행했으며 그 결과는 다음과 같습니다.



***Quick Sort Python***
   
|Comparison|Exchange|Time(ms)|
|----|----|----|
|100|19|0.0010006427764892578|
|200	|47	|0.0009996891021728516|
|500	|128	|0.0020003318786621094|
|1000	|200	|0.0050008296966552734|
|2000	|497	|0.010002613067626953|
|3000	|689	|0.01600360870361328|
|4000	|997	|0.02200460433959961|
|5000	|541	|0.027006864547729492|
   
각 input size에 맞는 리스트들의 원소는 python의 randint 함수를 사용해서 채워넣었습니다. randint 함수 기반의 random input generator에 의해 해당 리스트에 중복이 되는 원소가 들어가는 경우도 있어서 알고리즘을 작동시키는 매 시행마다 input size가 커진다고 해서 무조건 exchange 횟수와 알고리즘 실행 시간이 늘어나지는 않았습니다. 다만, input size가 커질수록 exchange 횟수와 알고리즘 실행 시간은 대체로 늘어나는 경향을 보입니다. Comparision 횟수는 퀵소트 알고리즘 이론과 동일하게 input size 만큼의 comparision연산을 수행한 것을 확인할 수 있었습니다.



해당 Python으로 구현된 퀵소트 알고리즘을 기반으로 총 3가지 각기 다른 pivot 선택 방법을 가진 새로운 퀵소트 알고리즘을 구현해 보았습니다. 구현한 3가지의 퀵소트 알고리즘은 다음과 같은 pivot 설정 방법을 가집니다.



 1. Input array의 첫 번째 원소를 pivot으로 설정하는 경우(quick_sort_first, partition_first)
 2. Low값과 high값의 사이에 있는 임의의 한 값을 pivot으로 설정하는 경우(quick_sort_random, partition_random)
 3. Low값가 high값의 가운데에 있는 값을 pivot으로 설정하는 경우(중간 값, quick_sort_mid, partition_mid)
구현한 퀵소트 알고리즘은 다음과 같습니다.

   
```
from random import randint
import time

# 이하 코드는 pivot 값을 맨 첫번째 값으로 정했을 때의 퀵정렬 알고리즘 이다.
def partition_first(arr, start, end, comp, exchange): # 오름차순으로 분배
    pivot = arr[start]
    L = start
    R = end
    done = False

    while not done:

        while L <= len(arr)-1 and arr[L] <= pivot: # comparison
            if L == len(arr)-1:
                break
            comp += 1
            L += 1

        while R >= 0 and pivot < arr[R]: # comparison
            if R == 0:
                break
            comp += 1
            R -= 1

        if R <= L:
            done = True

        else: # low < high -> swap
            exchange += 1
            arr[L], arr[R] = arr[R], arr[L]

    # change pivot and high -> swap
    exchange += 1
    arr[start], arr[R] = arr[R], arr[start]

    return R, comp, exchange


def quick_sort_first(arr, start, end, comp, exchange): # 오름차순으로 정렬
    if start < end:
        pivot, comp, exchange = partition_first(arr, start, end, comp, exchange)
        quick_sort_first(arr, start, pivot - 1, comp ,exchange)
        quick_sort_first(arr, pivot + 1, end, comp, exchange)
    return arr, comp, exchange

# 이하 코드는 pivot 값을 low 와 high 어느 사이의 값으로 정했을 때의 퀵정렬 알고리즘 이다.
def partition_random(arr, start, end, comp, exchange): # 오름차순으로 분배
    L = start
    R = end
    pivot = arr[randint(start,end)]
    done = False

    while not done:

        while L <= len(arr)-1 and arr[L] <= pivot: # comparison
            if L == len(arr)-1:
                break
            comp += 1
            L += 1

        while R >= 0 and pivot < arr[R]: # comparison
            if R == 0:
                break
            comp += 1
            R -= 1

        if R <= L:
            done = True

        else: # low < high -> swap
            exchange += 1
            arr[L], arr[R] = arr[R], arr[L]

    # change pivot and high -> swap
    exchange += 1
    arr[start], arr[R] = arr[R], arr[start]

    return R, comp, exchange


def quick_sort_random(arr, start, end, comp, exchange): # 오름차순으로 정렬
    if start < end:
        pivot, comp, exchange = partition_random(arr, start, end, comp, exchange)
        quick_sort_random(arr, start, pivot - 1, comp ,exchange)
        quick_sort_random(arr, pivot + 1, end, comp, exchange)
    return arr, comp, exchange

# 이하 코드는 pivot 값을 low 와 high 의 중간값으로 정했을 때의 퀵정렬 알고리즘 이다.
def partition_mid(arr, start, end, comp, exchange): # 오름차순으로 분배
    L = start
    R = end
    pivot = arr[(int)((start+end)/2)]
    done = False

    while not done:

        while L <= len(arr)-1 and arr[L] <= pivot: # comparison
            if L == len(arr)-1:
                break
            comp += 1
            L += 1

        while R >= 0 and pivot < arr[R]: # comparison
            if R == 0:
                break
            comp += 1
            R -= 1

        if R <= L:
            done = True

        else: # low < high -> swap
            exchange += 1
            arr[L], arr[R] = arr[R], arr[L]

    # change pivot and high -> swap
    exchange += 1
    arr[start], arr[R] = arr[R], arr[start]

    return R, comp, exchange


def quick_sort_mid(arr, start, end, comp, exchange): # 오름차순으로 정렬
    if start < end:
        pivot, comp, exchange = partition_mid(arr, start, end, comp, exchange)
        quick_sort_mid(arr, start, pivot - 1, comp ,exchange)
        quick_sort_mid(arr, pivot + 1, end, comp, exchange)
    return arr, comp, exchange
```
   
## 가설
알고리즘을 실행해서 결과를 얻기 전 3가지 방법 중 어느 방법이 가장 안정적이면서 빠른 수행 능력을 보여줄지 생각해 보았습니다. 이에 대해 제가 생각한 가설은 **pivot값을 low와 high의 중간에 위치하는 원소로 설정하는 것이 가장 안정적으로 정렬을 수행할 것이라고 생각**했습니다. 만약 pivot값을 첫 번째 원소로 설정한다면 정렬을 진행할 data들이 이미 정렬된 상태에 있을 때(원하는 정렬 결과는 오름차순 정렬인데 이미 내림차순으로 정렬이 되어 있을 경우) worst case time complexity를 가지기 때문에 이런 경우는 퀵정렬을 사용하는 것이 부적절하다고 생각했고 low와 high값 사이의 임의의 한 원소를 pivot으로 설정하면 그 사이의 임의의 값을 설정하는 알고리즘에 추가적인 시간 소요가 발생하여 실행 시간이 더 느려질 것이라고 예상되어 pivot을 low와 high의 중간 값으로 설정하는 것이 가장 바람직할 것이라고 생각했습니다.



### **실험 환경**
   
*Python 3.8*

*PyCharm 2020.2.2 (Professional Edition)*

*Runtime version: 11.0.8+10-b944.31 amd64*

*VM: OpenJDK 64-Bit Server VM by JetBrains s.r.o.*

*Windows 10 10.0*

*Memory: 1974M*

*Cores: 16*


   
## 실험 진행 및 결과
제가 python으로 구현한 퀵정렬 알고리즘은 random variable generator을 사용하기 떄문에 매 시행마다 일정하게 비례하는 결과를 보이지 않습니다. 때문에 총 5번 알고리즘을 실행시켰고 input array의 size는 n=3000으로 통일시켰습니다. 실험 결과는 다음과 같습니다.



 - 첫 번째 시행
   
|Pivot설정 방법|	Time(ms)|	Comparison|	Exchange|
|----|----|----|----|
|1st element|	0.01700305938720703|	3000	|383|
|Between low and high|	0.019004344940185547	|3000|	602|
|Mid element|	0.017003536224365234|	3000	|204|
 

 - 두 번째 시행
   
|Pivot설정 방법|	Time(ms)|	Comparison|	Exchange|
|----|----|----|----|
|1st element|	0.017003536224365234|	3000	|668|
|Between low and high|	0.0200045108795166|	3000|	627|
|Mid element|	0.017003774642944336|	3000	|358|
 

 - 세 번째 시행
   
|Pivot설정 방법|	Time(ms)|	Comparison|	Exchange|
|----|----|----|----|
|1st element|	0.01600337028503418|	3000	|263|
|Between low and high|	0.018004417419433594|	3000|	744|
|Mid element|	0.01800370216369629|	3000	|513|
 

 - 네 번째 시행
   
|Pivot설정 방법|	Time(ms)|	Comparison|	Exchange|
|----|----|----|----|
|1st element|	0.017003536224365234|	3000	|742|
|Between low and high|	0.019004344940185547	|3000	|725|
|Mid element	|0.01800370216369629	|3000	|748|
 

 - 다섯 번째 시행
   
|Pivot설정 방법|	Time(ms)|	Comparison|	Exchange|
|----|----|----|----|
|1st element	|0.01700425148010254	|3000	|186|
|Between low and high	|0.0200045108795166	|3000	|79|
|Mid element	|0.01800394058227539	|3000	|620|
   

다음은 random variable generator코드의 일부입니다.
   
```
# n = 3000, pivot = 1st elem
list_3000 = [randint(1, 3001) for i in range(3000)]
start_3000 = time.time()
list_3000, comp, exchange = quick_sort_first(list_3000, 0, len(list_3000)-1, 0, 0)
finish_3000 = time.time()
print("pivot = 1st element, n = 3000 time : ", finish_3000 - start_3000)
print("number of comparision : ", comp)
print("number of exchange : ", exchange)

# n = 3000, pivot = random elem
list_3000 = [randint(1, 3001) for i in range(3000)]
start_3000 = time.time()
list_3000, comp, exchange = quick_sort_random(list_3000, 0, len(list_3000)-1, 0, 0)
finish_3000 = time.time()
print("pivot = random element, n = 3000 time : ", finish_3000 - start_3000)
print("number of comparision : ", comp)
print("number of exchange : ", exchange)

# n = 3000, pivot = mid elem
list_3000 = [randint(1, 3001) for i in range(3000)]
start_3000 = time.time()
list_3000, comp, exchange = quick_sort_mid(list_3000, 0, len(list_3000)-1, 0, 0)
finish_3000 = time.time()
print("pivot = mid element, n = 3000 time : ", finish_3000 - start_3000)
print("number of comparision : ", comp)
print("number of exchange : ", exchange)
```
   
이하는 각 결과를 pivot 설정 방법에 따라 차트로 그 결과를 정리한 모습입니다. Number of comparision은 모두 n과 같은 값을 나타내므로 제외시켰고 수행 시간과 exchange 값의 결과의 균형을 맞추기 위해 Time 값에 10000을 곱해 차트로 나타내보았습니다.
   
<img src="https://github.com/bnbong/Myblog_posts/blob/master/posts/Study/20201228132415/first.png?raw=true" width="100%" height="30%" title="first" alt="first"></img>
<img src="https://github.com/bnbong/Myblog_posts/blob/master/posts/Study/20201228132415/second.png?raw=true" width="100%" height="30%" title="second" alt="second"></img>
<img src="https://github.com/bnbong/Myblog_posts/blob/master/posts/Study/20201228132415/third.png?raw=true" width="100%" height="30%" title="third" alt="third"></img>
<!-- ![first](https://github.com/bnbong/Myblog_posts/blob/master/posts/Study/20201228132415/first.png?raw=true)
![second](https://github.com/bnbong/Myblog_posts/blob/master/posts/Study/20201228132415/second.png?raw=true)
![third](https://github.com/bnbong/Myblog_posts/blob/master/posts/Study/20201228132415/third.png?raw=true) -->

   
위 그래프의 결과에 따른 각 pivot 설정 방법에 따라 알고리즘 실행 시간과 exchange 횟수의 평균을 내본 결과는 다음과 같습니다.


   
|Pivot 설정방법	|Time(ms * 10000)	|Exchange
|----|----|----|
|1st element|	168.032|	448.4|
|Between low and high|	192.04|	555.4|
|Mid element	|176.03	|488.6|


## 결과 분석
l  **Pivot을 첫 번째 element 로 설정하는 경우**: 세 가지의 Pivot 설정 방법을 적용시킨 알고리즘 중 제일 적은 알고리즘 실행시간을 보여줬던 시행이 있었으며(세 번째 시행), 평균적으로 다른 두 방법에 비해 적은 시간이 소요된 것을 볼 수 있었습니다. 다만, Exchange가 이루어진 횟수는 각 시행마다 눈에 띄는 차이가 있었으나, Pivot을 low와 high 사이의 임의의 한 element로 설정하는 경우의 그것과는 차이가 적었습니다. Exchange횟수가 두 번째로 많았던 시행 또한 존재했습니다(네 번째 시행).



l  **Pivot을 low와 high 사이의 임의의 한 element로 설정하는 경우**: 다른 두 방법에 비해 알고리즘 실행시간이 제일 길었으며, Exchange가 이루어진 횟수 또한 급격한 차이가 발생한 것을 확인할 수 있었습니다(5번째 알고리즘 실행결과 참고). 알고리즘 실행 시간이 늘어난 이유로 추측하자면, 제가 작성한 Python Quicksort 코드의 경우 Pivot을 설정하는 과정에 random number generator을 추가로 사용했기 때문인 것으로 추측됩니다. 다시 말해 Pivot을 random으로 설정하는 과정에 추가적인 시간소요가 있었음을 예상할 수 있었습니다.



l  **Pivot을 low와 high의 중간에 있는 element로 설정하는 경우**: Pivot을 설정하는 세가지의 방법 중 알고리즘 실행시간 및 Exchange 횟수의 평균 모두 중간정도의 기록을 남겼습니다.



## 결론
제가 시행한 실험에서는 **pivot값을 첫 번째 element값으로 설정하는 것이 가장 빠르고 가장 적은 exchange를 수행한 알고리즘**이라는 결과가 나왔습니다. 이는 제 가설과는 다른, 제 3자가 보기에는 pivot을 mid element로 설정하는 것 보다 효율적인 알고리즘이라고 판단할 수 있는 결과입니다.

 

그러나 pivot을 첫 번째 element로 설정하는 알고리즘은 quicksort알고리즘의 worst time complexity를 발생시킬 여지가 있습니다. 정렬을 해야 하는 data들은 수도 없이 많이 있고, 그 data들 중에서 이미 정렬이 된 data가 없으리라는 보장이 없기 때문에, 저는 이 ‘만에 하나’라는 경우도 고려해서 대부분의 상황에서 효율적인 정렬을 수행하는 알고리즘이 제일 좋은 알고리즘이라고 생각합니다.





알고리즘은 전공자에게도 굉장히 머리아픈 컴퓨터과학 주제라고 생각합니다. 저도 백준같은 알고리즘 사이트에서 적지 않은 알고리즘 문제를 풀어보았지만 이번처럼 단순히 문제 풀이를 위한 알고리즘 공부가 아니라 개념으로 배웠던 내용에 대해 궁금한 점을 직접 실험을 통해 궁금증에 대한 결과를 얻어봤던 이번 경험은 소소하게 재미있었던 경험이었습니다. 
