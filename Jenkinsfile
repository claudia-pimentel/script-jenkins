pipeline
{ 
    agent { node ('agent-01')} 
            parameters {
        string(name: 'branch_to_build', defaultValue: 'master')
    }
    stages{ 
        stage ('Clone repo') {
            steps{
        //bat "git config core.longpaths true"
                git branch: "master", url: "https://github.com/claudia-pimentel/dotnetcore-testproj"
                }
                             }
    stage('Build') { 
        steps{
        echo "Running build"
            }
                    }
    }
}
