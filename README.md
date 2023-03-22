# react js hello world 2023 + github actions deployment

reacj hello world for 2023

note: this is borrowed from my react js project, available, here, https://github.com/Jay-study-nildana/FrontEndForStudents/tree/main/ReactJSForStudents/helloworld2023

# things to remember

1. even if your app runs just fine, locally, you will get a lot of problems when you deploy.
1. I had to use "build": "CI=false && react-scripts build". usually, the "CI=false" is not neccessary, if your react code is perfect and has zero warnings. mine has a lot of warnings, and I did not want to fix it.
1. unit tests. I did not want any unit tests to run. so, I removed the 'test' section from package.json.
1. you have to make sure, you 'zip' the deployment files. Otherwise, build will take 40 to 50 minutes to complete. same with deployment. check, 'azurereactjs.yaml' for more details
    ```
    - name: Zip artifact for deployment
      run: zip release.zip ./* -r

    - name: Upload artifact for deployment job
      uses: actions/upload-artifact@v3
      with:
        name: node-app
        path: release.zip

    - name: Download artifact from build job
      uses: actions/download-artifact@v3
      with:
        name: node-app

    - name: unzip artifact for deployment
      run: unzip release.zip          
    ```
1. now, even after all this, you will not have build errors. but, you will still get plenty of deployment errors.
1. timeouts can happen.
1. the target web app might not be powerful enough, storage, RAM, network bandwidth on azure, to perform the deployment. 
1. the deployment step can take anywhere from 10 to 20 minutes. 

# References

1. https://stackoverflow.com/questions/62663451/treating-warnings-as-errors-because-process-env-ci-true-failed-to-compile
1. https://stackoverflow.com/questions/69400583/github-actions-artifact-is-taking-to-much-to-deploy-in-azure-web-apps
1. https://stackoverflow.com/questions/68470162/how-to-archive-files-in-artifact-for-github-workflow-actions-in-order-to-fix-thi
1. https://docs.github.com/en/actions/deployment/deploying-to-your-cloud-provider/deploying-to-azure/deploying-nodejs-to-azure-app-service
1. https://medium.com/projectwt/github-actions-vanilla-js-bootstrap-azure-web-app-f17a24418321

# Hire Me

I work as a full time freelance coding tutor. Hire me at [UpWork](https://www.upwork.com/fl/vijayasimhabr) or [Fiverr](https://www.fiverr.com/jay_codeguy). 

# Hobbies

I try to maintain a few hobbies.

1. Podcasting. You can listen to my daily life [podcast](https://stories.thechalakas.com/listen-to-podcast/).
1. Podcasting. You can listen to my movies [podcast](https://sandkdesignstudio.in/jays-movie-podcast/).
1. Photography Nature. You can see my photography on [Unsplash](https://unsplash.com/@jay_neeruhaaku).
1. Photography Fashion. You can see my fashion photography on [Behance](https://www.behance.net/vijayasimhabr)
1. Digital Photorealism 3D Art. You can see my work on [ArtStation](https://www.artstation.com/jay_kalenildana).
1. Daily Life Blog. [Read it here](https://medium.com/the-sanguine-tech-trainer).
1. Coding and Technology Blog. [Read it here](https://medium.com/projectwt).
1.  Daz 3D, Photography and Photoshop Blog. [Read it here](https://medium.com/random-pink-hula).

# important note 

This code is provided as is without any warranties. It's primarily meant for my own personal use, and to make it easy for me share code with my students. Feel free to use this code as it pleases you.

1. Jay's [Developer Profile](https://jay-study-nildana.github.io/developerprofile)
1. Jay's [Personal Site](https://stories.thechalakas.com/)