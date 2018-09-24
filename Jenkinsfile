//def checkPath(github_repo_path, environment) 
//{
  //def result;
  
  // This is a somewhat naive implementation, but it's sandbox safe
  
  //if(repo_path == null || repo_path.length() == 0)
  //{
//    echo ("Require Github repo path parameter")
 // }
  //else{
    //  echo "Repo_path is provided"
  //}
  //if(environment == null)
  //{
    //echo ("Require environment parameter")
  //}
  //else{
    //  echo "Environment is provided"
  //}
  
//  return result
//}
node{
    //defining the parameters
    parameters{
            stringParam(defaultValue: '', description: '', name: 'github_org') 
            stringParam(defaultValue: '', description: '', name: 'github_repo')
            stringParam(defaultValue: '', description: '', name: 'github_repo_path')
            stringParam(defaultValue: '', description: '', name: 'github_repo_branch')
            stringParam(defaultValue: '', description: '', name: 'environment')
             }

    // This stage checks to make sure the pipeline has been supplied the correct parameters.
    stage('Validation') {
            println "=============================================="
            println "Stage1:Validation"
            println "=============================================="
            /*echo "Github Org: ${params.github_org}"
            echo "Github Repo: ${params.github_repo}"
            echo "Github Repo Path: ${params.github_repo_path}"
            echo "Github branch: ${params.github_branch}"
            echo "Environment: ${params.environment}"
            echo "Before if loop"*/
            /*if("${params.github_org}" == null || "${params.github_org}".length() == 0){
                echo "enteered first if loop"
                echo "Github_org parameter is provided"
                if("${params.github_repo_branch}" == null || "${params.github_repo_branch}".length() == 0){
                     echo "enteered second if loop"
                    echo "Github_repo_branch parameter is provided"
                }
                else{
                     echo "enteered second else loop"
                    echo "Missing parameter:github_repo_branch"
                }
            }
            else{
                 echo "enteered first else loop"
                echo "Missing parameter:Github_org"
            }
    
            
           
            if(("${params.github_org}" == null || "${params.github_org}".length() == 0) && 
            ("${params.github_repo}" == null || "${params.github_repo}".length() == 0) &&
            ("${params.github_repo_path}" == null || "${params.github_repo_path}".length() == 0) &&
            ("${params.github_repo_branch}" == null || "${params.github_repo_branch}".length() == 0) &&
            ("${params.github_repo_path}" == null || "${params.github_repo_path}".length() == 0))
            {
                echo "Missing parameters"
            }
            else
            {
                echo "All parameters are provided"
            }
            */
          
            if("${params.github_org}" == null || "${params.github_org}".length() == 0 ){
                echo "In if loop"
                echo "Missing parameter: Please provide the github_org"
            }
            else{
                echo "In else loop"
                echo "Git hub org Parameter is provided"
            }
            if("${params.github_repo}" == null || "${params.github_repo}".length() == 0 ){
                echo "In if loop"
                echo "Missing parameter: Please provide the github_repo_"
            }
            else{
                echo "In else loop"
                echo "Git hub repo Parameter is provided"
            }
            if("${params.github_repo_path}" == null || "${params.github_repo_path}".length() == 0 ){
                echo "In if loop"
                echo "Missing parameter: Please provide the github_repo_path"
            }
            else{
                echo "In else loop"
                echo "Git hub repo path Parameter is provided"
            }
             if("${params.github_repo_branch}" == null || "${params.github_repo_branch}".length() == 0 ){
                echo "In if loop"
                echo "Missing parameter: Please provide the github_repo_branch"
            }
            else{
                echo "In else loop"
                echo "Git hub repo branch Parameter is provided"
            }
            
            if("${params.environment}" == null || "${params.environment}".length() == 0 ){
                echo "In if loop"
                echo "Missing parameter: Please provide the environment"
            }
             else{
                echo "In else loop"
                echo "Environment Parameter is provided"
            }
            
            /*def myParam = false
            if (params.myParam != null){
                    myParam = params.myParam
            }
            else{
                echo "Missing parameter"
            }
            checkPath(github_repo_path, environment)
            
           fileExists 'sainavya5/pipeline.git'
             then echo "The file exists in given github repo path: $github_repo_path"*/
            echo "Entering my list"
            //creating list for parameters
            MYLIST = []
                    MYLIST += "${params.github_org}" 
                    MYLIST += "${params.github_repo}"
                    MYLIST += "${params.github_repo_path}"
                    MYLIST += "${params.github_repo_branch}"
                    MYLIST += "${params.environment}"

                    for (def element = 0; element < MYLIST.size(); element++) {
                            //check if each parameter is provided
                           if(MYLIST[element] == null || MYLIST[element].length() ==0)
                           {
                               echo "The parameter missing is: ${MYLIST[element]} "
                           }
                            else
                            {   
                                echo "The parameter validated is: ${MYLIST[element]} "
                            }
                    }
                    
                    
            MYTESTLIST = []
                    MYTESTLIST += "github_org"
                    MYTESTLIST += "github_repo"
                    MYTESTLIST += "github_repo_path"
                    MYTESTLIST += "github_repo_branch"
                    MYTESTLIST += "environment"
                    echo "Before mytestlist"
                    for (def element = 0; element < MYTESTLIST.size(); element++) {
                            //check if each parameter is provided
                            echo "+++entered MYTESTLIST+++"
                           if(MYTESTLIST[element] == null || MYTESTLIST[element].length() ==0)
                           {
                               echo "The parameter missing is: ${MYTESTLIST[element]} "
                           }
                            else
                            {   
                                echo "The parameter validated is: ${MYTESTLIST[element]} "
                            }
                    }
                         //  for (int i = 0; i < list.size(); i++) {
        //sh "echo Hello ${list[i]}"
                          // def browsers = ['chrome', 'firefox']
                    /*for (int i = 0; i < browsers.size(); ++i) {
                        echo "Testing the ${browsers[i]} browser"*/
                           
                    
    }
        
    stage('checkout'){
        println "=============================================="
        checkout([$class: 'GitSCM', 
        branches: [[name: '*/master']], 
        doGenerateSubmoduleConfigurations: false, 
        extensions: [], 
        submoduleCfg: [], 
        userRemoteConfigs: [[credentialsId: 'b74b58be-f128-46ed-8d02-5f7965517a99', url: 'https://github.com/sainavya5/pipeline.git']]])
        println "=============================================="
       sh 'cat index.html'
    }
    stage('Validate_Paths')
    {
        sh 'cd pipeline || ls'
    }
 
    
    //This will check the terraform code syntax
    stage('Lint') {
            println "=============================================="
            println "Stage2:Lint"
            
            //sh ''' 
            //   set +e
            //    echo "testing echo in an sh block that is not assigned to a variable"
            //'''
            
            
            
            println "=============================================="
    }
    //a compliance stub for future use
    stage('Compliance') {
            echo "=============================================="
            println "Stage3:Compliance"
            echo "=============================================="
    }
    //a security stub for future use
    stage('Security') {
            echo "=============================================="
            println "Stage4:Security"
            echo "=============================================="
    }
    //execute the terraform init stage
    stage('Terraform-init') {
            echo "=============================================="
            println "Stage5:Terraform-init"
            echo "=============================================="
    }
    //execute the terraform plan
    stage('Terraform-plan') {
            echo "=============================================="
            println "Stage6:Terraform-plan"
            echo "=============================================="
    }
    //execute the terraform apply
    stage('Terraform-apply') {
            echo "=============================================="
            println "Stage7:Terraform-apply"
            echo "=============================================="
    }
    //produce a report for display regarding the results
    stage('Report'){
            echo "=============================================="
            println "Stage8:Reporting results"
            echo "=============================================="
    }
}


