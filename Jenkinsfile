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
        dir (".\\sonarqube-scanner-msbuild\\CSharpProject\\") {
            bat 'C:\\Users\\admin\\Downloads\\sonar-scanner-msbuild-4.4.2.1543-net46\\SonarQube.Scanner.MSBuild.exe begin /k:\"icare_teste1\" /d:sonar.host.url=\"http://localhost:9000\" /d:sonar.login=\"1c4fe35571a9acb83c8d0a5a8addf9a2ac6c8d5c\"'
            bat 'C:\\Windows\\Microsoft.NET\\Framework\\v4.0.30319\\MSBuild.exe /t:Rebuild /p:Configuration=Release;OutDir=C:\\custom_build_out'
            bat 'C:\\Users\\admin\\Downloads\\sonar-scanner-msbuild-4.4.2.1543-net46\\SonarQube.Scanner.MSBuild.exe end /d:sonar.login=\"1c4fe35571a9acb83c8d0a5a8addf9a2ac6c8d5c\"'
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
