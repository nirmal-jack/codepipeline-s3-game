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



