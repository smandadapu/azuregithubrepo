
def GITHUB_PROJECT = “https://github.com/smandadapu/azuregithubrepo.git”

def GITHUB_BRANCH = ‘${env.BRANCH_NAME}’

node any
{
stages {
stage (“Listing Branches”) 
{
echo “Initializing workflow”
//checkout code
echo "GITHUB_PROJECT"
git url: GITHUB_PROJECT
sh ‘git branch -r | awk \'{print $1}\’ ORS=\’\\n\’ >branches.txt’
sh ”’cut -d ‘/’ -f 2 branches.txt > branch.txt”’
//sh “sed s’/origin”\’///g branches.txt > branch.tx”
//sed ‘s/$/from S0 to S1/’
}
stage(‘get build branch Parameter User Input’) 
  {

liste = readFile ‘branch.txt’
echo “please click on the link here to chose the branch to build”
env.BRANCH_SCOPE = input message: ‘Please choose the branch to build ‘, ok: ‘Validate!’,
parameters: [choice(name: ‘BRANCH_NAME’, choices: “${liste}”, description: ‘Branch to build?’)]
}
}
}
