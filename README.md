# 研究日誌

在這個專案中<br>
我用文字檔紀錄 ： <br>
<ul>
  <li>整體系統架構軟體位置</li>
  <li>塵封多年被我挖掘出來的發現</li>
  <li>依時間排列的紀錄</li>
</ul>

<h1>整體系統架構軟體位置</h1><br>
<b>3 cars controller </b>D:\JERWEN\3Car_0324show1\Test\3carshow0413_1.cpp<br>
<b>MATLAB主檔</b> D:\JERWEN\show_single0108\partial_path\Deformation\mytest999modefynoloop.m<br>
<b>分群初始化 </b>C:\Users\User\Documents\Visual Studio 2010\Projects\test<br>

<h1>發現</h1>
null<br>

<h1>依時間排列</h1>
<h4>(2017/08/05)</h4>endNote 和 mathtype 可以當成office 的插件，打論文、方程式很方便<br><br>
<h4>(2017/08/07)</h4>在練習建構DLL file 的時候出現LINK : fatal error LNK1123
solution : <a href = "https://xiaolaba.wordpress.com/2013/09/01/link-fatal-error-lnk1123-%E8%BD%89%E6%8F%9B%E6%88%90-coff-%E6%99%82%E5%A4%B1%E6%95%97-%E6%AA%94%E6%A1%88%E7%84%A1%E6%95%88%E6%88%96%E6%90%8D%E6%AF%80/">LINK : fatal error LNK1123: 轉換成 COFF 時失敗: 檔案無效或損毀</a><br><br>
<h4>(2017/08/08)</h4>
#include <opencv2/opencv.hpp> 和 #include <opencv2/core/core.hpp> 似乎有相同定義的資料結構 比如說: Mat
Mat 好像可以當作 inputArray outputArray<br><br>

<h4>(2017/09/03)</h4>
如何使用以及產生.lib file , .dll file<br>

1.>>cl /c app.cpp (/c : compile without linking, only .obj file is generated)<br>
2.>>cl /c func1.cpp<br>
3.>>cl /c func2.cpp<br>
4.現在你可以看到在資料夾中出現 app.obj 和 func1.obj func2.obj<br>
5.>>link /out:program.exe app.obj func1.obj func2.obj<br>
6.>>program.exe (執行產生的執行檔)<br>
7.>>lib /out:funcs.lib func1.obj func2.obj (產生.lib file)<br>
8.>>link /out:program.exe app.obj funcs.lib (linking)<br>
9.>>program.exe<br>
<br>
說明:LIB 和 DLL 的差別在於，LIB直接編入程式，但是DLL只在程式執行時，才開始尋找DLL檔
所以這將導致，如果將遠本的DLL檔案改名，執行檔恐會出現不能執行的狀況<br>

<h4>(2017/09/04)</h4><br>
int variable; --->宣告一個 int variable<br>
int func(...);--->宣告一個 int function --->int(...) func其實才是更好的表是形態<br>
另外 函式本身就具有隱性指標的含意 也就是說  (*func)(...) 等價  func(...)<br>
typedef int (*func)();//在全域中必須這樣使用<br>
int (*func)();//在函式中可以這樣使用<br>

reference : http://www.programmer-club.com.tw/ShowSameTitleN/c/25059.html<br>

請問typedef of function pointer 
<h4>(2017/09/29)</h4><br>
what is overhead?<br>
It's the resources required to set up an operation. It might seem unrelated, but necessary.<br>

It's like when you need to go somewhere, you might need a car. But, it would be a lot of overhead to get a car to drive down the street,<br> so you might want to walk. However, the overhead would be worth it if you were going across the country.<br>

In computer science, sometimes we use cars to go down the street because we don't have a better way, or it's not worth our time to <br>"learn how to walk".<br>

<h4>(2017/09/29)</h4><br>
<h3>c++ concurrency in action NOTE</h3>

when it comes to concurrency, it refer to the following two things.<br>
one is multithread in one process.<br>
the other is multi single-threaded processes<br><br>

the book "c++ concurrency in action " focus on the first scenario.<br>
it seems that the utilization of multi-core hardware is another thing.<br>
but, over all , speak of the speed up of program. Hardware multithread is the one we discussed.<br><br>

in the past,programmers saw their program got faster without any effort on their part.<br>
Now,it's defferent. <br>
<br>
it is imprtant to know when to or not to use the concurrency.<br>
concurrency is just like other optimization strategy.<br>
too many threads might make computer busy doing switching between tasks which lower the program.<br>
also,the resource is limited,though there is a tool called thread pool to limit the number of threads.<br>
but there are no silver bullet.it got its own problem.<br>
in the perspective of maintainence,the code using multitthread is always hard to understand.<br><br>

The declarations for the multithreading
support in the Standard C++ Library are in new headers<br>: the functions and
classes for managing threads are declared in <thread>,<br> whereas those for protecting
shared data are declared in other headers.<br><br>
