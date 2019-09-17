<pre>
set -e
"Exit immediately if a simple command exits with a non-zero status."

echo 192 | awk '{printf "%X", $1}'

 ifconfig | grep Bcast | cut -f 2 -d ":" | sed 's/\./ /g' > /mnt/ramdisk/ip
awk '{printf "%X %X %X %X", $1, $2, $3, $4}' /mnt/ramdisk/ip

ifconfig | grep Bcast | cut -f 2 -d ":" | sed 's/\./ /g' | sed '2d' | awk '{printf "%X %X %X %X", $1, $2, $3, $4}'

PATH=/bin:/sbin:/usr/bin:/usr/sbin:/usr/local/bin:/usr/local/sbin:~/bin
export PATH

echo -e "Please input a filename, I will check the filename's type and permission. \n\n"
read -p "Input a filename : " filename
test -z ${filename} && echo "You MUST input a filename." && exit 0
test ! -e ${filename} && echo "The filename '${filename}' DO NOT exist" && exit 0
test -f ${filename} && filetype="regulare file"
test -d ${filename} && filetype="directory"
test -r ${filename} && perm="readable"
test -w ${filename} && perm="${perm} writable"
test -x ${filename} && perm="${perm} executable"
echo "The filename: ${filename} is a ${filetype}"
echo "And the permissions for you are : ${perm}"

[ -z "${HOME}" ] ; echo $?

/path/to/scriptname  opt1  opt2  opt3  opt4
       $0             $1    $2    $3    $4

read -p "Please input (Y/N): " yn

which wpa_cli
if [ "$?" != 0 ]; then
    echo wpa_cli is not found.
    exit 1
fi

if [ "${yn}" = "Y" ] || [ "${yn}" = "y" ]; then
  echo "OK, continue"
elif [ "${yn}" = "N" ] || [ "${yn}" = "n" ]; then
  echo "Oh, interrupt!"
else
  echo "I don't know what your choice is"
fi


case ${1} in
  "hello")
    echo "Hello, how are you ?"
    ;;
  "")
    echo "You MUST input parameters, ex> {${0} someword}"
    ;;
  *)   # 其實就相當於萬用字元，0~無窮多個任意字元之意！
    echo "Usage ${0} {hello}"
    ;;
esac


function printit(){
  echo "Your choice is ${1}"   # 這個 $1 必須要參考底下指令的下達
}

while [ "${yn}" != "yes" -a "${yn}" != "YES" ]
do
  read -p "Please input yes/YES to stop this program: " yn
done
echo "OK! you input the correct answer."


while true
do
  command
done

while true; do command; sleep 5; done


users=$(cut -d ':' -f1 /etc/passwd)    # 擷取帳號名稱
for username in ${users}               # 開始迴圈進行！
do
  id ${username}
done

network="192.168.1"              # 先定義一個網域的前面部分！
for sitenu in $(seq 1 100)       # seq 為 sequence(連續) 的縮寫之意
do
# 底下的程式在取得 ping 的回傳值是正確的還是失敗的！
  ping -c 1 -w 1 ${network}.${sitenu} &> /dev/null && result=0 || result=1
# 開始顯示結果是正確的啟動 (UP) 還是錯誤的沒有連通 (DOWN)
  if [ "${result}" == 0 ]; then
    echo "Server ${network}.${sitenu} is UP."
  else
    echo "Server ${network}.${sitenu} is DOWN."
  fi
done

filelist=$(ls ${dir})        # 列出所有在該目錄下的檔案名稱
for filename in ${filelist}
do
  perm=""
  test -r "${dir}/${filename}" && perm="${perm} readable"
  test -w "${dir}/${filename}" && perm="${perm} writable"
  test -x "${dir}/${filename}" && perm="${perm} executable"
  echo "The file ${dir}/${filename}'s permission is ${perm} "
done
</pre>
