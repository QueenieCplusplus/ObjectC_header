# ObjectC_header
標頭檔

所謂的標頭檔案，是指一個原始檔案 src 可以將另外一個 src 檔案的全部內容包含進來，即將另外的 header 到本檔案中。

Header 是 ObjC 前置處理程式的重要功能之一。

重要指令

                #import <檔案名稱>

也可以用雙引號

                #import "檔案名稱"

關係示意圖


      fileA.c             fileB.c                 a src
                   +                   = 
        a src               b src                 b src
        
實際範例

QQQ.h 

標頭檔案是一個檔案名稱

              #import <Foundation/Foundation.h>
              
              @inerface QQQ: NSobject
              {
              
                 int q;
              
              }
              -(void)setQ;
              -(void)printQ;
              
              @end

QQQ.m

在別的檔案中注入此標頭
實施他類別的方法
並實作他的方法
如無此檔包含
黨包含 目的是進行具現化物件
則編譯時會出現錯誤訊息替史
     
             #import"QQQ.h"
             
             @implementation QQQ
             -(void)setQ
             {
                q=99;
             }
             
             -(void)printQ
             {
                NSlog(//...,q);
             }
             
             @end
             
main.m

在別的源代碼中注入此標頭
並且引用其方法

              #import<Foundation/Foundation.h>
              #import"QQQ.h"
              
              int main(int argc, const char * argv[])
              {
              
                @autoreleasepool{
                
                  QQQ *b=[[QQQ alloc]init];
                  [b setQ];
                  [b printQ];
                
                }
               
                return0;
              }
