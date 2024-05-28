# codepipeline-s3-game
# Continuous Deployment using AWS Code Pipeline and S3

--Code for a game is hosted in GitHub.  We can create an S3 bucket for static website hosting, then create a continuous deployment pipeline (using AWS Code Pipeline) to automatically deploy the code whenever changes are made. --

## The Game
A simple memory matching game.  The user clicks two cards (images of memes) to try to match them.  If there's a match, the cards disappear from the board.  If there's no match, the cards are flipped back to their blank side so the user can try again.

The game consists of HTML, CSS and JavaScript.

## The Deployment Environment
The code will be deployed and hosted in S3.

## The Deployment Pipeline
The pipeline is created using AWS Code Pipeline.  The pipeline pulls the code from GitHub, and deploys it to S3 whenever a change is detected in the code.

************************************
- login to AWS Console and create a S3 Bucket name "my-meme-game28"
  ![s3 bucket](https://github.com/nirmal-jack/codepipeline-s3-game/assets/170439621/76dfe03d-2e09-4987-9fbc-2a9e14e7fca2)

- go inside the bucket and click on properties, scroll all the way down and choose enable option in "static website hosting"


  ![image](https://github.com/nirmal-jack/codepipeline-s3-game/assets/170439621/647b53cd-363d-4324-adbd-844d272e8784)


- Click on the option enable and give the name of the html file ... "index.html" and click on save changes.

  ![static1](https://github.com/nirmal-jack/codepipeline-s3-game/assets/170439621/337dda31-7e1b-4c25-a740-beb551230242)


- the other change we need to make is on the "permissions". we have initially all public access to the website, but if we need players to play the game, we should add, "Bucket Policy". write the policy and save changes

  ![bucket policy](https://github.com/nirmal-jack/codepipeline-s3-game/assets/170439621/6e8e4b70-2d10-4c98-9eb3-cdfd04aae491)

  - now we got our code in github, the s3 bucket is setup and permission is give for static website hosting with a bucket policy, now we need to create a code pipeline that will orchaestrate getting the code from github and upto the bucket.
 
  - Headover to the aws console and open AWS CODEPIPELINE. Click on create pipeline
    .
    ![create pipeline](https://github.com/nirmal-jack/codepipeline-s3-game/assets/170439621/92daeb67-8076-4941-95d9-5facb021dd78)

  - Give a name to the pipeline like "meme-pipeline" and select v1, because v1 is sufficient for this project.
![create](https://github.com/nirmal-jack/codepipeline-s3-game/assets/170439621/ad95fda4-be95-4717-871b-c801d3d2a2d1)

    
  - Click on "new service role", give the name and give next.

    ![create1](https://github.com/nirmal-jack/codepipeline-s3-game/assets/170439621/7030135f-fba0-4d1e-ad30-905ca64224c8)


  - for the source provider, choose github (version 2) and then choose "Connect to github". Here we need to connect github to AWS Codepipeline
    ![source](https://github.com/nirmal-jack/codepipeline-s3-game/assets/170439621/ca4d1198-7b96-4892-8b61-b8b6225cca4d)

 - give a name like "meme-github-connect"
    ![connect](https://github.com/nirmal-jack/codepipeline-s3-game/assets/170439621/98ae0b43-0c71-4d33-adc1-de08d4b2e950)


    - then select "install a new app" to make the connect from github to AWS Codepipeline
   
      
      ![installanew](https://github.com/nirmal-jack/codepipeline-s3-game/assets/170439621/ee6ce4ac-4f08-49db-a19d-1c5ba4018a9c)

      - the personal github account opens, here we can choose select a repository and give the repo for the game.
        ![github](https://github.com/nirmal-jack/codepipeline-s3-game/assets/170439621/e0a03940-66c0-4cb7-8f21-7e4ba4437402)


      








