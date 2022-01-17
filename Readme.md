//versi == snapshot, setiap snapshot menghasilkan hash
//hash  : urutan kode unik kombinasi dari author, hash sebelumnya, dan message
//head  : pointer ke hash terbaru
************************************************************************************

//Setup
git config --global user.name "Muhammad Nur Ilmi"
git config --global user.email "mnurilmi18@gmail.com"
git config --global core.editor "code --wait"
git config --global diff.tool "default-diftool"
git config --global difftool.default-difftool.cmd "code --wait --diff \$LOCAL \$REMOTE"

git config --list --show-origin

//Buat repo
git init
cd .. //untuk keluar master
git status

//The three states
1. modified : mengubah,menambah,menghapus namun belum tersimpan ke repo
2.staged    : menandai file yang akan disimpan ke repo
3.commited  : data sudah aman di repo permanen

//The three section
1. working directory
2. staging area
3. repo

//Add
git Add nama_file
git add .

//commit
git commit nama_file -m "message"
git commit . -m "message"

//menghapus
delete di vsCode
git add nama_file
git commit nama_file -m 'message'

//menghapus dari working directori
git clean -f

//membatalkan perubahan di working directori
git restore nama_file

//membatalkan staging index
git restore --staged nama-nama_file
git restore nama_file

//setelah dicommit tidak bisa direstore
-reset commit-revert commit

//Log setiap commit
git Log
git log --oneline
git log --oneline --graph
git show <hash> 

//compare
git diff hash1 #hash2
git difftool <hash1> <#hash2>

//rename, operasi delete dan tambah file baru
rename file
git add nama_file


//reset commit
git reset <mode>
mode:
1.--soft    :memindahkan pointer tapi tidak menghapus perubaahan di staging dan working direktori
2.--mixed   :staging index diubah tapi working direktori masih tetap
3.--hard    :saat memintahkan pointer, working staging direktori mengikuti pointer head
//contoh:
5d58cd3 (HEAD -> master) merename file2.txt menjadi file_2.txt
e4ddc2b file 3 dihapus
0a3c387 commit smeua perubahan
0c2038a file 1 diubah
f123173 ubah file3
52c5372 menambah file3.txt
1908061 nambah file1.txt
//
git reset --soft e4ddc2b
git reset --soft 5d58cd3


//amend commit
git commit --amend

//checkout
git checkout <hash>

//revert commit, membatalkan commit
git revert <hash>

//ignore
-sebutin nama file di file *.gitignore

//blame
-digunakan untuk mencari tahu siapa yang menambahkan commit tersebut

//ALIAS
-menambahkan perintah lain untuk mempersingkat suatu perintah
git config --global alias.ko commit
git config --global alias.komit commit
git config --global alias.logone 'log --oneline'

//REMOTE
git remote <link>