# Unity-ready-to-Git
This repo is ready to go as is. Empty project correctly configured.


Preview how to set-up UNITY project on GitHub on your own. (Source: stackoverflow)

The steps:

Create a git repo on-line (eg. github.com)
Save your Unity project on your local filesystem
Enable External option in Unity › Preferences › Packages › Repository (only if Unity ver < 4.5)
Switch to Visible Meta Files in Edit › Project Settings › Editor › Version Control Mode
Switch to Force Text in Edit › Project Settings › Editor › Asset Serialization Mode
Save scene and project from File menu.
Quit Unity and then delete the Library and Temp directory in the project directory.
Delete everything but the Assets and ProjectSettings directory.
Make your first commit. Open terminal and follow the next 6 steps.

cd to/your/unity/project/folder

git init

git add *

git commit -m "First commit"

git remote add origin git@github.com:username/project.git

git push -u origin master

Open your Unity project while holding down the Option or the left Alt key. This will force Unity to recreate the Library directory (this step might not be necessary since I've seen Unity recreating the Library directory even if you don't hold down any key).

Make git ignore the Library and Temp directories so that they won’t be pushed to the server. Add them to the .gitignore file and push the ignore to the server. Remember that you'll only commit the Assets and ProjectSettings directories.
And here's my own .gitignore recipe for my Unity projects (I work on a Macbook):

# =============== #
# Unity generated #
# =============== #
Temp/
Obj/
UnityGenerated/
Library/
Assets/AssetStoreTools*

# ===================================== #
# Visual Studio / MonoDevelop generated #
# ===================================== #
ExportedObj/
*.svd
*.userprefs
*.csproj
*.pidb
*.suo
*.sln
*.user
*.unityproj
*.booproj

# ============ #
# OS generated #
# ============ #
.DS_Store
.DS_Store?
._*
.Spotlight-V100
.Trashes
Icon?
ehthumbs.db
Thumbs.db
