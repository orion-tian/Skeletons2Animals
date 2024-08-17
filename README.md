# Skeletons 2 Animals AI

An AI that takes in animal skeleton images and outputs images of what the animal should look like. While this doesn't seem that exciting for common animals like cats and horses, we believe this AI could be very fun when applied to extinct creatures such as dinosaurs to see how they would look like. This project was heavily inspired by this AI project: https://github.com/VladPVas/Skeletons_N_Animals However, we decided to use a different machine learning architecture to increase the number of training images the AI can take in to hopefully improve on this project's resuts. 

![Screenshot 2024-08-16 at 6 55 11 PM](https://github.com/user-attachments/assets/b23da9ce-7c63-4932-b7e7-698ca60625f5)

We decided to use the cycleGAN machine learning architecture: 
![Screenshot 2024-08-16 at 6 53 57 PM](https://github.com/user-attachments/assets/bb670f85-3757-4f9d-beb8-f6f9ca118726)

Because in this way, we would no longer need paired training data of an animal skeleton and the resulting animal. Instead, we can simply have a lot of animal skeletons and a lot of unrelated animal images by using the cycleGAN architecture, which turns the outputted animal image back into a skeleton image to make sure the AI produces realistic looking animals that resembles the original skeleton image. In this way, we are able to get a lot more training data, which will hopefully improve the results of the AI.  

## Results

![Screenshot 2024-08-16 at 7 01 56 PM](https://github.com/user-attachments/assets/7401d931-396d-41d2-a88d-0f5d509a35f2)
![Screenshot 2024-08-16 at 7 12 29 PM](https://github.com/user-attachments/assets/220b7e3f-1303-4fa1-9677-be2218ba24bb)
![Screenshot 2024-08-16 at 7 15 50 PM](https://github.com/user-attachments/assets/8531cdbd-ec1c-404c-9c7a-10c5161ba9b7)
![Screenshot 2024-08-16 at 7 02 09 PM](https://github.com/user-attachments/assets/1aaea82c-f85d-48d1-973c-0de9c4151bdd)

We ran the training for approximately 500 generations, and in that time the AI was able to figure out side view quadeuped skeletons well. This is most likely because this is the most common type of skeleton image in the dataset. As the training went on, the AI progressed from adding splotches of color randomnly, to envoloping the whole skeleton, to finally following the bones closer to deffrentiate the body from the legs and head.

![Screenshot 2024-08-16 at 7 04 53 PM](https://github.com/user-attachments/assets/cc1abc16-3c8c-4282-a2ea-9319785c84d3)

The AI did struggle with fish skeletons and more realistic photos intead of just drawings. But the main issue of our model is that the skeleton is still clearly remaining in the genereated animal image. We tried changing the loss function. Decreasing the loss of the cycled skeleton image seemed to work well as the model was punished less for not reproducing the original skeleton exactly. We also tried incorporating a binary skeleton classifier as port of discriminator loss to punish the model if a skeleton is visible in the output animal. 

Further improvements to the AI would require getting more data and more varied data than mainly quadreped skeletons from the side. We could also get the skeleton binary classifier to work or transfer learn from another model that deals with animal skeletons. 

