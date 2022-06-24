# Hello-World-CI-CD-Github-Actions
This repo contains my first step Android CI-CD with GitHub Action, Firebase distribution, and Sonarcloud.

# Getting Started 

This repo setup a **CI** pipelines using [**Github Actions**](https://github.com/features/actions) :octocat: and **CD** using [**Firebase Distribution**](https://firebase.google.com/docs/app-distribution) ⚡

# GitHub Actions - CI/CD Terms

  * [Github Actions](https://resources.github.com/downloads/What-is-GitHub.Actions_.Benefits-and-examples.pdf)

    > GitHub Actions gives developers the ability to automate their workflows across issues, pull requests, and more—plus native CI/CD functionality.

  * [Continuous Integration](https://en.wikipedia.org/wiki/Continuous_integration)

    > Is the practice of merging all developers' working copies to a shared mainline several times a day.

 * [Continuous Delivery](https://en.wikipedia.org/wiki/Continuous_delivery)

    > Is a software engineering approach in which teams produce software in short cycles, 
    > ensuring that the software can be reliably released at any time and, when releasing the software, without doing so manually.


# Workflows 

  * [main.yaml](https://github.com/karimelbahi/Hello-World-CI-CD-Github-Actions/blob/main/.github/workflows/main.yml) : This workflow have to check for lint, unit testing, istrumentation testing, build apk,and static code analyzer, and deploy to firebase distribution

## Let's Start With CI

  * To start with build CI pipelines have to create a new `YAML` file, then you could setup your workflow, checkout this for more details [Metadata syntax for GitHub Actions](https://docs.github.com/en/actions/creating-actions/metadata-syntax-for-github-actions)
 
### Info to creat create your own workflow
   * Name

      > Name of your workflow 

   * on 

     > Control when the workflow will be triggerd

   * jobs
   
     > Jobs are a set of steps that execute on the same runner. Each runs in its own VM and parallel to other jobs, unless otherwise specified.

        * Job Name
   
            > Pick Up your job name.

        * Needs
   
            > To make the current job wait another one (sequential principle).

        * Runners
   
            > A runner is a GitHub Actions server. It listens for available jobs, runs each in parallel, and reports back progress, logs and
             results. Each runner can be hosted by GitHub or self-hosted on a localized server. GitHub Hosted runners are based on Ubuntu Linux,
             Windows, and macOS.

        * Steps
   
            > ESteps are individual tasks that run commands in a job. These can be an action or a shell command. All steps in a job execute on the same runner.
            > Determine a sequence of tasks will be executed for each job.
        
        * Uses
   
            > A step parameters, and use it to install environment or a repo from any marketplace.

        * Run

            > One of step parameters, you can use it when your are trying to hit a command.
         
      * [Checkout](https://github.com/marketplace/actions/checkout) : This action checks-out your repository under `$GITHUB_WORKSPACE`, so your workflow can access it.
      * [Setup Java JDK](https://github.com/marketplace/actions/setup-java-jdk) : Set up Java JDK.
      * [Upload Build Lint Report](https://github.com/marketplace/actions/upload-a-build-artifact) : This uploads artifacts from your workflow allowing you to share data between jobs and store data once a workflow is complete.

## Let's Start With CD

   * To build CD pipelines, have to integrate the application with **Firebase Distribution** or any other marketplace.

      > Firebase Distribution is used to distributing the app to QA team Automatically after all jobs succeeded. 

   * Build Gradle : Build an APK.
   * [Firebase Distribution](https://firebase.google.com/docs/app-distribution): integrate your app with firebase distribution.
   * [Firebase CLI reference](https://firebase.google.com/docs/cli): The Firebase CLI (GitHub) provides a variety of tools for managing, viewing, and deploying to Firebase projects..
   * appId : Get it from your project settings on firebase console.
   * token : Get it buyg Runing this command `firebase login:ci`.
   * Secrets : To encrypt the sensitive information, have to access it from **Settings/Secrets Tab**, for more info checkout out [Encrypted Secrets](https://docs.github.com/en/actions/security-guides/encrypted-secrets)

   #### Screenshot from firebase distribution dashboard after sending an APK to the QA team!:rocket:	
