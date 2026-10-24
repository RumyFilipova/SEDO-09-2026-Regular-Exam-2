pipeline{
    agent any
    stages{
        stage("Restore dependencies"){
            when{
                    anyOf{
                        branch "main"
                        }
                }
            steps{
            
                bat "restore dependencies"
            }
           
        }
        stage("Build the project"){ when{
                    anyOf{
                        branch "main"
                        }
                }
            steps{
                bat "dotnet build --no-restore"
            }
           
        }
        stage("Run the tests"){
                when{
                    anyOf{
                        branch "main"
                        }
                }
            steps{
                bat "dotnet test --no-build --verbosity normal"
            } 
        }
    }
}