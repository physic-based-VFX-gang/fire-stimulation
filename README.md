# 專案 Setup 紀錄
1. 創建 Unreal 專案加入 [.gitignore](https://github.com/github/gitignore/blob/main/UnrealEngine.gitignore)
2. 使用  Git Large File Storage ([教學1](https://medium.com/projectwt/setting-up-git-large-file-storage-for-unreal-engine-projects-1854d6337177), [教學2](https://forum.gamer.com.tw/Co.php?bsn=60607&sn=11))
    ```
    git lfs install
    ```
    [教學1](https://medium.com/projectwt/setting-up-git-large-file-storage-for-unreal-engine-projects-1854d6337177) 的 .gitattributes
    ```
    # UE file types
    *.uasset filter=lfs diff=lfs merge=lfs -text
    *.umap filter=lfs diff=lfs merge=lfs -text

    # Raw Content types
    # 3D models 
    *.fbx filter=lfs diff=lfs merge=lfs -text
    *.3ds filter=lfs diff=lfs merge=lfs -text
    # Raw Image file of softwares 
    *.xcf filter=lfs diff=lfs merge=lfs -text
    *.psd filter=lfs diff=lfs merge=lfs -text
    # usual files
    *.png filter=lfs diff=lfs merge=lfs -text
    *.mp3 filter=lfs diff=lfs merge=lfs -text
    *.wav filter=lfs diff=lfs merge=lfs -text
    *.jpg filter=lfs diff=lfs merge=lfs -text
    ```
    - `filter`: repo 不存本體存 pointer to lfs
    - `diff`: 改由 lfs 紀錄版本差異
    - `merge`: merge branch 也是由 lfs 操作
    - `-text`: 標記不是 text file, 是 binary
3. 創 github repo
4. Unreal 中 `Tools > connect to Revision Control`，用 github 網址設定 remote (origin)，不要創建 README 與 .gitignore，Initial Commit 下去
5. `git add .` & `git commit` 確保 .gitignore 與 .gitattributes 有進去 
6. push to github  
    ```
    git push -u origin main
    ```
7. 暫時完成! 如果之後出問題，我們再想辦法修正 or 重新來過
