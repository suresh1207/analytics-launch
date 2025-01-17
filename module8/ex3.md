## Exercise 8.3 - Model Training and Experimentation

So you’ve prepared your data, authored your model and packaged it to test it at scale as a recipe. Now let’s go ahead and train and test the model.

The URL to login to Adobe Experience Platform is: [https://platform.adobe.com](https://platform.adobe.com)

### Exercise 8.3.1 - Train a Model based on a Recipe

Login to Adobe Experience Platform: [https://platform.adobe.com](https://platform.adobe.com)

![DSW](./images/home.png)

From the left menu, click on ```Models```.

![DSW](./images/mlmodels.png)

In this exercise, we'll use a prebuilt recipe to make product recommendations.
In the top menu, click on ```Recipes```.

![DSW](./images/recipes.png)

In Recipes, you'll find multiple recipes. Look for your own recipe in the list, which should be named ```ldapRecommendations```.

![DSW](./images/prrecipe.png)

Click the ```ldapRecommendations``` - recipe to open it.

![DSW](./images/prrecipe1.png)

You now need to create your own Model, based on the ```ldapRecommendations``` - recipe.
To do that, click on the ```Create a Model``` - button.

![DSW](./images/createmodel1.png)

To train this model, you need to provide it with an Input Dataset. In our case, you generated data for this Input Dataset in exercise 1 and the input dataset now contains information around product purchase data.
The dataset to use is called ```Recommendations Input Dataset```. Select it from the list.

![DSW](./images/input.png)

Click ```Next``` to continue.

![DSW](./images/next.png)

In the next step, you need to define a name for your Model. As a naming convention, let's use: ```ldap -  Recommendations Model``` and replace **ldap** by your ldap.

Example: for ldap vangeluw, the name become ```vangeluw - Recommendations Model```.

![DSW](./images/modelname.png)

We can also hypertune the Model by changing the Model Configuration. To do that, you can change the number of recommendations and the sampling fraction.

![DSW](./images/modelcfg.png)

If you want to update the Model's Configuration parameters, double-click one of the parameters and give it a new value.

For instance, I'd like to have 3 recommendations with a sampling fraction of 0.8.

![DSW](./images/params.png)

After changing these values, click ```Finish``` to finish your configuration.

![DSW](./images/finish.png)

After a couple of seconds, you'll be reverted back to the Model's homepage where you'll see a Training Run 1 with a status of ```Pending```. The process to finish the training run can take 5+ minutes.

![DSW](./images/trainingrunp.png)

After 1-2 minutes, your Training Run's status will change to ```Running```.

![DSW](./images/trainingrunrunning.png)

And 1-2 minutes later, the Training Run's status will change to ```Complete```.

![DSW](./images/trainingrunsuccess.png)

Once the Training Run has completed, you'll see a couple of metrics that indicate the quality of the run:

  * **Recall** is also known as True Positive Rate and also as Sensitivity: if the real result was Yes, how often did the model predict Yes?
  
  ![DSW](./images/recall.png)
  
  * **Precision** means: When the model predicts Yes, how often is it correct?
  
  ![DSW](./images/precision.png)

Training a model requires more then one run. All Training Runs will be visible on this page and you'll be able to compare their results, so you can decide which one is the most successfull. 
![DSW](./images/multipleruns.png)

After training your model, let's now score it in the next exercise.

---

Next Step: [Exercise 8.4 - Scoring and Consumption of Insights](./ex4.md)

[Go Back to Module 8](../README.md)

[Go Back to All Modules](../../README.md)