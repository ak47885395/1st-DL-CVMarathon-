# 1st-DL-CVMarathon-
Day001_HW
# question Number one:
1.檔案資料會包成檔案提供下載，格式可能包含常用的標準格式，例如「CSV」、「JSON」等等通用的格式。
2.開放接口（API）提供程式化的連接的接口，讓工程師/分析師可以選擇資料中要讀取的特定部分，而不需要把整批資料事先完整下載回來
3.網頁爬蟲資料沒有以檔案或 API 提供，但出現在網頁上。可以利用爬蟲程式，將網頁的資料解析所需的部分。
檔案 & API 是由資料擁有者主動釋出，爬蟲則是資料擁有者被動公開的。
# question Number two:
# 根據需求引入正確的 Library
from urllib.request import urlretrieve
import os
# 下載檔案到 Data 資料夾，存成檔名 Homework.txt
try :
        os.makedirs( './Data' ,exist_ok =True )
        urlretrieve("https://www.w3.org/TR/PNG/iso_8859-1.txt" , "Homework.txt")
except :
        print("error")
# 檢查 Data 資料夾是否有 Homework.txt 檔名之檔案
files = ('./Data/Homework.txt')

if ("Homework.txt") in files:
    print ('O Data 資料夾有 Homework.txt 檔名之檔案')
else :
    print ('X Data 資料夾沒有 Homework.txt 檔名之檔案')
# 將「Hello World」字串覆寫到 Homework.txt 檔案
with open('./Data/Homework.txt' , "w") as fh:
    fh.write('Hello World')
try:
    with open('./Data/Homework.txt' , "r") as fh:
        print(fh.readlines())
except EnvironmentError: # parent of IOError, OSError *and* WindowsError where available
    pass   
 fh=open('./Data/Homework.txt' ,  "r")
fh_text=fh.read()
print(len(fh_text))
if len('Hello World') == len(fh_text):
    print('[O] 檢查 Homework.txt 檔案字數是否符合 Hello World 字數')
else:
    print('[X] 檢查 Homework.txt 檔案字數是否符合 Hello World 字數')
