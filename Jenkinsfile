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

    parameters{
            stringParam(defaultValue: '', description: '', name: 'github_org') 
            stringParam(defaultValue: '', description: '', name: 'github_repo')
            stringParam(defaultValue: '', description: '', name: 'github_repopath')
            stringParam(defaultValue: '', description: '', name: 'github_repo_branch')
            stringParam(defaultValue: '', description: '', name: 'environment')
             }

    // This checks to make sure the pipeline has been supplied the correct parameters.
    stage('Validation') {
            println "=============================================="
            println "Stage1:Validation"
            println "=============================================="
            echo "Github Org: ${params.github_org} is validated"
            echo "Github Repo: ${params.github_repo}is validated"
            echo "Github Repo Path: ${params.github_repo_path} is validated"
            echo "Github branch: ${params.github_branch} is validated"
            echo "Environment: ${params.environment} is validated"
            echo "Before if loop"
            if("${params.github_repo_path}" == null || "${params.github_repo_path}".length() == 0 ){
                echo "In if loop"
                echo "Missing parameter: Please provide the github_repo_path"
            }
            else{
                echo "In else loop"
                echo "Git hub repo path Parameter is provided"
            }
            if("${params.environment}" == null || "${params.environment}".length() == 0 ){
                echo "In if loop"
                echo "Missing parameter: Please provide the environment"
            }
             else{
                echo "In else loop"
                echo "Environment Parameter is provided"
            }
            
            //def myParam = false
            //if (params.myParam != null){
            //        myParam = params.myParam
            //}
            //else{
            //    echo "Missing parameter"
            //}
   //         checkPath(github_repo_path, environment)
            
           // fileExists 'sainavya5/pipeline.git'
             //   then echo "The file exists in given github repo path: $github_repo_path"

    }  
    //stage("Checkout"){
        
        //checkout(
        //[$class: 'GitSCM', branches: [[name: '*/master']],
        //doGenerateSubmoduleConfigurations: false,
        //extensions: [],
        //submoduleCfg: [],
        //userRemoteConfigs: [[credentialsId: 'personal_access_token', url: 'zzzzzzzz']]
        //])
        
    stage('checkout'){
        println "=============================================="
        checkout([$class: 'GitSCM', 
        branches: [[name: '*/master']], 
        doGenerateSubmoduleConfigurations: false, 
        extensions: [], 
        submoduleCfg: [], 
        userRemoteConfigs: [[credentialsId: 'b74b58be-f128-46ed-8d02-5f7965517a99', url: 'https://github.com/sainavya5/pipeline.git']]])
        println "=============================================="
       // sh cat index.html
    }
 
    
    //This will check the terraform code syntax
    stage('Lint') {
            println "=============================================="
            println "Stage2:Lint"
            
            sh ''' 
                set +e
                echo "testing echo in an sh block that is not assigned to a variable"
            '''
            
            
            
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


