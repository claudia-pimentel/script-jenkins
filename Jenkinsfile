agent { node { label 'agent-01' } { 
    parameters {
        string(name: 'branch_to_build', defaultValue: 'master')
    }
    stage('Clone repo') {
        //bat "git config core.longpaths true"
        git branch: "master", url: "https://github.com/claudia-pimentel/dotnetcore-testproj"
    }
    stage('Build') { 
        echo "Running build"
        sh 'dotnet test'
                    }
}
      }
