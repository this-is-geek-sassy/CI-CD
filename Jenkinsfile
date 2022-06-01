pipeline {

    agent any

    stages {

        stage("git pull") {

            steps {

                echo "Pulling latest codes from master ..."
                echo "Pulling engine code ..."

                sh """
                    cd /opt/whitesource/repos/engine/oed_engine
                    git pull
                """

                echo "Pulling database code ..."

                sh """
                    cd /opt/whitesource/repos/db/prd_utilities
                    git pull
                """

                echo "Pulling tool code ..."

                sh """
                    cd /opt/whitesource/repos/tool/oed_tool
                    git pull
                """

                echo "Pulling scheduler code ..."

                sh """
                    
                """

                echo "Pulling upgrade code ..."

                sh """
                    
                """
            }
        }
        stage("name change") {

            steps {

                echo "changing the file name for the ncessary scans ... "
            }
        }
        stage("scan") {

            steps {

                echo "Scanning db libraries ..."

                sh """
                    java -jar wss-unified-agent.jar -d "/opt/whitesource/repos/db/prd_utilities/prd-db/libs"
                """
            }
        }
        stage("email triggering") {

            echo "Triggering email to the recipients ..."
        }

    }

}