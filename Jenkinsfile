pipeline{
    agent any
    stages{
        stage("Restore dependencies"){
            steps{
                when{
                    anyOf{
                        branch "main"
                        }
                }
                bat "restore dependencies"
            }
           
        }
        stage("Build the project"){
            steps{
                when{
                    anyOf{
                        branch "main"
                        }
                }
                bat "dotnet build --no-restore"
            }
           
        }
        stage("Run the tests"){
            steps{
                when{
                    anyOf{
                        branch "main"
                        }
                }
                bat "dotnet test --no-build --verbosity normal"
            } 
        }
    }
}