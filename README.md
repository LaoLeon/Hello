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
(2017/08/05)endNote 和 mathtype 可以當成office 的插件，打論文、方程式很方便<br><br>
(2017/08/07)在練習建構DLL file 的時候出現LINK : fatal error LNK1123
solution : <a href = "https://xiaolaba.wordpress.com/2013/09/01/link-fatal-error-lnk1123-%E8%BD%89%E6%8F%9B%E6%88%90-coff-%E6%99%82%E5%A4%B1%E6%95%97-%E6%AA%94%E6%A1%88%E7%84%A1%E6%95%88%E6%88%96%E6%90%8D%E6%AF%80/">LINK : fatal error LNK1123: 轉換成 COFF 時失敗: 檔案無效或損毀</a><br><br>
(2017/08/08)
#include <opencv2/opencv.hpp> 和 #include <opencv2/core/core.hpp> 似乎有相同定義的資料結構 比如說: Mat
Mat 好像可以當作 inputArray outputArray<br><br>

(2017/09/03)
如何使用以及產生.lib file , .dll file<br><br>

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
所以這將導致，如果將遠本的DLL檔案改名，執行檔恐會出現不能執行的狀況

