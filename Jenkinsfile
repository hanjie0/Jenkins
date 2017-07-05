stage('test_CMD') 
{
    node('master')
    {
        timestamps
        {
            bat '''
                echo %workspace%
                if not exist %workspace%\results mkdir %workspace%\results
                for /f %%i in ('uname') do echo %%i
                for /f %%i in ('hostname') do set HOST=%%i
                echo %NODE_NAME%
                if not %NODE_NAME%==%HOST% echo 'the node label is not the same as the hostname'
                if exist %workspace%\results (
                    echo 'Y'
                    ) else (
                    echo 'N'
                    )
                    
                '''
        }
    }
}

stage('buildJob_test4Build')
{
    node('master')
    {
        timestamps
        {
            build job: 'test4Build', parameters: [string(name: 'testType', value: 'UT')]
        }
    }
        

}