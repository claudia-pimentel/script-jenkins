node { 
    parameters {
        string(name: 'repo_url', defaultValue: 'http://foo.bar/baz.git', description: 'Git repo URL')
        string(name: 'branch_to_build', defaultValue: 'master', description: 'Repo branch to build from')
    }
    stage('Clone repo') {
        //bat "git config core.longpaths true"
        git branch: "${branch_to_build}", credentialsId: "${credentials_to_use}", url: "${repo_url}"
    }
    stage('Build') { 
        echo "Running build"
        bat '/usr/share/dotnet'
                    }
    }
    stage('Packaging'){
        echo "Running packaging tool"
        //bat "powershell.exe -NonInteractive -ExecutionPolicy Bypass -Command \"Compress-Archive C:\\custom_build_out\\_PublishedWebsites C:\\custom_build_out\\pack.zip \""
    }
    stage('Deploy') {
        echo "Publishing"
    }
}
