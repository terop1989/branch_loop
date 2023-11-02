node {

    stage("Clean"){
        deleteDir()
    }

    stage("Making dir") {
        sh "mkdir 222"
    }

    dir("222") {
        git url: "https://github.com/terop1989/service01.git"
        sh "git branch -l"
    }
}