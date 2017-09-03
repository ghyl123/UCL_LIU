# UCL_LIU
利用python+pyhook開發的仿蝦米，肥米輸入法<br>
<br>
<center>
  <img src="screenshot/ucl_2.png">
  <img src="screenshot/demo.gif">
</center>
<br>
作者：羽山秋人 (<a target="_blank" href="http://3wa.tw">http://3wa.tw</a>)<br>
<br>
最初開發日期：2017-06-16 11:24<br>
最後更新日期：2017-08-02 10:10
<br>
版本：V 0.1<br>
<br>
下載位置：<br>
　　主程式：<a download target="_blank" href="https://raw.githubusercontent.com/shadowjohn/UCL_LIU/master/dist/uclliu.exe">https://raw.githubusercontent.com/shadowjohn/UCL_LIU/master/dist/uclliu.exe</a><br>
　　同音字庫：<a download target="_blank" href="https://raw.githubusercontent.com/shadowjohn/UCL_LIU/master/dist/pinyi.txt">https://raw.githubusercontent.com/shadowjohn/UCL_LIU/master/dist/pinyi.txt</a><br>　　
<br>
<br>
開發動機：<br>
　　吃飽閒閒覺得人生就是該自己寫一套輸入法，然後就開始寫了。<br>
字碼表說明：<br>
　　　　由於字碼表的版權問題爭議，就不放 liu.json 了，liu.json 的格式同PIME的架構。<br>
　　要好的字碼表的話，請買正版，將 tab->cin->json <br>
　　雖然很麻煩，但沒人想因為實作一套輸入法就被告翻。<br>
　　<br>
　　P.S: 請不要使用守義大學FTP裡的那個 liu-uni.tab ，太古早了，而且有些字根都錯的!
　　<br>
　　首次使用如果沒有liu.json，會自動進行 tab->cin->json的轉換，tab會自動查找C:\windows\Syswow64\liu-uni.tab<br>
　　或同目錄下的tab檔。
<br>
開發工具：<br>
  <ul>
    <li>Python 27 (32BIT)</li>
    <li>pyhook</li>
    <li>pygtk</li>
    <li>pywin32</li>
    <li>pyinstaller 可搭配build.bat製作dist/uclliu.exe檔</li>
    <li>psutil 用來判斷目前視窗跑什麼，如果是putty、pietty、pcman出字方式要調整</li>
    <li>(Third party) php.py 羽山比較熟php，所以在python裡實作很多php的函式</li>
    <li>(Third party) portalocker.py 防重複執行，會Lock c:\temp\UCLLIU.lock</li>
    <li>(Third party) SendKeysCtypes.py 可以送出Unicode的SendKeys</li>
    <li>(Third party) liu_unitab2cin.py 可以將tab轉成cin的檔案，改成支援python2.7的寫法</li>
    <li>(Third party) cintojson.py 可以將cin轉成json的檔案，改成支援python2.7的寫法</li>
    <li>(Third party) cin\phone.cin 同音字表參考新酷音的傳統注音表:https://raw.githubusercontent.com/google/jscin/master/src/tables/phone.cin</li>
    <li>字碼表亦可參考PIME裡的liu.json</li>
</ul>
<br>
編譯：<br>
　　pip install pyinstaller<br>
    可參考 build.bat 製作單檔 exe<br>
<br>
使用方法：<br>
　　1、您可以只下載dist/uclliu.exe<br>
　　2、將 「liu-uni.tab 或 liu.cin 或 liu.json」任一種檔案 與 uclliu.exe 放一起<br>
　　3、執行 uclliu.exe 即可開始使用<br>
　　4、首次執行，系統會自動將tab轉成liu.json，需要花大概30秒~1分鐘的時間，之後有liu.json就可以快速開啟。<br>    
　　5、未來使用的話，就把uclliu.exe、作好的字根檔liu.json帶著走，四處都能打肥米輸入法了A_A<br> 
　　(還是要再強調一次，不要用義守大學FTP裡的那個liu-uni.tab，建議可以安裝正版嘸蝦米後在C:\windows\Syswow64裡找到)
　　(新版的嘸蝦米，liu-uni.tab可能會放在 C:\Program Files\BoshiamyTIP 這裡面)<br>
　　6、如果需要使用如「'ucl」這種同音字查詢，請將 dist\pinyi.txt 也與uclliu.exe 放一起<br>
<br>       
ToDo：<br>
<ul>
  <li>(Done)<s>1、(嚴重)「送出字元」的方法，試了很多send key一直無法解決 send unicode的問題，暫時使用「剪貼簿」的Ctrl+V來實作貼上文字的功能</s></li>
  <li>(Done 2017-07-16)<s>2、「英文全形」輸入時，有些組合鍵如 Alt+tab還尚未決定</s></li>
  <li>(Done)<s>3、py2exe包成一支exe</s>改用pyinstaller代替</li>
  <li>4、尚有些按鍵會讓「英/肥」切來切去，暫未處理</li>
  <li>(Done)<s>5、離開程式的按鈕</s></li>
  <li>(Done)<s>6、支援V鍵選第二個字</s></li>
  <li>(Done)<s>7、「」【】這種框框應該也要支援</s></li>
  <li>(Done)<s>8、sendkey時，判斷window id，如果該id是putty、pcman，改成shift+ins作文字貼上</s></li>
  <li>(Done)<s>9、「英/半」時，加上調整opacity值，讓肥米變透明(Opacity 0.2)</s></li>
  <li>(Done)<s>10、增加提示沒有liu.json時的錯誤警告</s></li>
  <li>11、輸出字後，可以[提示簡根字]，以便提升打字速度</li>
  <li>(Done 2017-07-18)<s>12、同音字查詢，使用 pinyi.txt</s></li>
  <li>(Done 2017-07-12)<s>13、寫一篇如何把tab->cin->json的教學(已有自動轉檔了)</s></li>
  <li>(Done)<s>14、支援把tab跟UCLLIU放一起就可以自動使用、轉檔的功能</s></li>
  <li>15、缺碼查詢，如lom[、lom]</li>
  <li>(Done 2017-07-15)<s>16、在「英/全」的模式時，無法按 Shift 切換回「肥/全」</s></li>
  <li>(Done 2017-07-31)<s>17、在「肥/全」的「冒號、分號、空白」應該是要出全形字</s></li>
  <li>18、tab->cin->json有點久，所以預計再加一個字根檔轉換中的進度畫面</li>
  <li>(Done 2017-07-13)<s>19、V鍵出字，有些字如果V是尾根，會有打不出來的問題，如「截」jaqv，會變成「戟」，「截」會完全打不出來。回(oov)，變成要打「ooo2」</s></li>
  <li>(Done 2017-07-13)<s>20、修正打錯字根時，後面的字沒清掉的問題</s></li>
  <li>(Done 2017-07-13)<s>21、修正用滑鼠點「肥/英」時，字根未清除的問題</s></li>
  <li>(Done 2017-07-13)<s>22、修正pcman出字的問題，貼在上時設一下delay才不會貼的時候剪貼簿的東西一直跑出來</s></li>
  <li>23、增加啟動時版本提示，有助於確認目前版本，之後版號會開始增加</li>
  <li>(Done 2017-07-14)<s>24、修正全螢幕下，如看影片，下排工作列佔著畫面的問題，去除肥米執行時下方多一個taskbar</s></li>
  <li>(Done 2017-07-17)<s>25、字根不可超過五碼</s></li>
  <li>(Done 2017-07-16)<s>26、英/全時，修正刪除鍵可以正常使用</s></li>
  <li>(Done 2017-07-17)<s>27、在錯誤的字碼按下空白鍵，會刪掉已輸入的字碼，且游標不會前進</s></li>
  <li>28、切到「肥」模式時，系統應自動強制切換輸入法為「Eng」</li>
  <li>(Done 2017-07-18)<s>29、同音字過多分頁的問題，要支援按空白鍵下頁</s></li>
  <li>(Done 2017-07-31)<s>30、首次執行uclliu.exe時，如果連續執行uclliu.exe，會造成在轉換cin、json發生異常</s></li>
  <li>(Done 2017-07-31)<s>31、支援新版嘸蝦米liu-uni.tab放置位置 C:\Program Files\BoshiamyTIP\liu-uni.tab</s></li>
  <li>(Done 2017-08-02)<s>32、「肥」模式時，當按著win鍵+英文，應該要允許出字，不然無法按如 win+r 這種功能</s></li>  
  <li>33、支援Linux、Mac的研究(下一次吃飽閒閒再說)</li>    
</ul>
<br>
版權：<br>
　免錢的 MIT-License
