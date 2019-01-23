node { 
    parameters {
        string(name: 'branch_to_build', defaultValue: 'master')
    }
    stage('Clone repo') {
        //bat "git config core.longpaths true"
        git branch: {dotnetcore-testproj}, url: {'https://github.com/claudia-pimentel/dotnetcore-testproj'}
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
