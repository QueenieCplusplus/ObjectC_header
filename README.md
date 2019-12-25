# ObjectC_header
標頭檔

所謂的標頭檔案，是指一個原始檔案 src 可以將另外一個 src 檔案的全部內容包含進來，即將另外的 header 到本檔案中。

Header 是 ObjC 前置處理程式的重要功能之一。

重要指令

                #import <檔案名稱>

也可以用雙引號

                #import "檔案名稱"

關係示意圖


      fileA.c             fileB.c               #import <a.h>
                   +                   = 
        a src               b src                 b src
        
        
