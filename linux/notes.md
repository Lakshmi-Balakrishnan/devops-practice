# Linux troubleshooting notes.
lakshmi practice.
## Disk full....
- df -h              check which filesystem is full
- df -ih             check if inodes are full
- du -h --max-depth=1 /path    find which folder is big
- find /path -type f -size +500M    find large files
- truncate -s 0 file.log    empty a log file safely

## Port conflict
- sudo lsof -i :PORT -sTCP:LISTEN    find who owns the port
- kill PID           stop it gracefully
- kill -9 PID        force stop

#27/10/2026
PROJECT START WITH GIT& GITHUB 
step1: check git is installed
 git --version
step2: set you identity
 git config --global  user.name "Lakshmi"
 git config --global user.email "your@email.com"
 git config --global --list
step 3: sethup SSH key For Github
ls ~/.ssh/id_ed25519.pub
If it says No such file, run this to create one:
ssh-keygen -t ed25519 -C "your@email.com"
Press Enter three times to accept defaults. Then:
cat ~/.ssh/id_ed25519.pub
AAAAC3NzaC1lZDI1NTE5AAAAIJtabFSeydjznk0ckqbaQ0VtDKa/q+dxVyAPfOUbIUJU lakshimibalakrishnan2003@gmail.com
github profile add 
Field	Value
Title	Lakshmi Laptop
Key type	Authentication Key
Key	ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAINR9EAC6S92U+02n7VMY38T3cCPxPU5mvd8eEzQn7jSg lakshimibalakrishnan2003@gmail.com

Click Add SSH key, then run:
ssh -T git@github.com


#o
now create first repo
step 1: github.com top right
     2. new repository
     3. repository name devops interview practice ,visibility :public
        do not tick "add README"  
     4.create
step 2:
 mkdir ~/devops-practice cd 
 git init
 git branch -M main
 echo "#DEVOPS Practice journal" > README.md
 git add READ.md
 git commit -m "first commit"

step 3: connect to github and push
git remote add origin git@github.com:Lakshmi-Balakrishnan/devops-practice.git
git push -u origin main   

step 4: verify
git log --oneline (or) git log --oneline --graph 
git remote -v
Expected output of git remote -v:
origin  git@github.com:Lakshmi-Balakrishnan/devops-practice.git (fetch)
origin  git@github.com:Lakshmi-Balakrishnan/devops-practice.git (push)


NEXT :BRANCHING AND MERGING
cd ~/devops-practice1
git switch -c feature/git-notes
new branch name feature/git-notes
  
mkdir git
cat > git/notes.md << 'EOF'
helloo today
ctrl +c exit
also use nano 
 
git add .
git commit -m "my notes"
git push origin feature/git-notes


THEN MERGE IT BACK TO MAIN 
git swith main
git merge feature/git-notes
git push origin main
git log --oneline --graph


o






      















  
 















