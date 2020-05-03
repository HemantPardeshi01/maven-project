pipeline
{
    agent any
    stages
    {
        stage('Source Code Checkout ')
        {
            steps
            {
                git credentialsId: 'hemant', url: 'https://github.com/HemantPardeshi01/maven-project.git'
            }
        }
        
        stage('Compile Code')
        {
            steps
            {
                withMaven(jdk: 'java_jdk', maven: 'localmvn') 
                {
                    bat "mvn compile -DskipTests"
                }
            }
        }
        
        stage('Test Code')
        {
            steps
            {
                withMaven(jdk: 'java_jdk', maven: 'localmvn') 
                {
                    bat "mvn test"
                }
            }
        }
        
        stage('Build')
        {
            steps
            {
                withMaven(jdk: 'java_jdk', maven: 'localmvn') 
                {
                    bat "mvn clean install"
                }
            }
        }
        
    }
}
