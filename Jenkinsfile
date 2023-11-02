@NonCPS
def getBranchNames(project){
    project.getItems().each { job ->
        echo job.getProperty(org.jenkinsci.plugins.workflow.multibranch.BranchJobProperty.class).getBranch().getName()
    }
}

node {
    // Clean workspace before doing anything
    deleteDir()
    try {
        stage ('Clone') {
            getBranchNames(jenkins.model.Jenkins.instance.getItem(env.JOB_NAME.minus("/${env.JOB_BASE_NAME}")))
            echo "done reading jobs"
        }
    } catch (err) {
        error "BUILD FAILED: ${err}"
    }
}