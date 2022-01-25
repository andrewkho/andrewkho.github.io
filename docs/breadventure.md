---
layout: page
title: Breadventure
permalink: /breadventure/
---

Sept 2018, updated Oct 2021

[github](https://github.com/andrewkho/breadventure)

Back in 2018 I was looking for an excuse to do some NLP with recurrent neural networks.
I like baguettes, so I decided to try and train one to generate Bread recipes.
Not really knowing what I was doing, I sort of guessed that recipes (and bread recipes) had a specific enough structure and repetitive enough ingredients that it might work with not a lot of data.

## Models

In 2018, I used LSTMs and Pytorch, getting decent results from my 3GB desktop GPU. The LSTM was able to learn the recipe structure: Title, small free-form blurb, list of ingredients, and then baking instructions. 
None of the recipes were actually bakable.

In 2021, I wanted to try this out again with a Pre-trained Transformer. 
I ended using the HuggingFace library and, wow, it was way easier this time around to get up and running.
Things have come such a long way in such a short time.
I was severely limited by the 3GB desktop GPU and the only model I was able to fit on there for fine-tuning was `distilgpt2`.
The results were somewhat better than the 2018 version, although not by miles. I think the main thing I noticed was it had a better time keeping track of specific ingredients in the blurb, ingredients list, and directions.

I'm pretty sure these recipes would do much better with the larger models. If only I wasn't too cheap to rent a cloud GPU...

## Generated recipes

Here's a couple of recipes I cherry-picked from the `distilgpt2` model, fine-tuned with the recipe data. I gave it the prompt "Sourdough Country Loaf" and "The Spanish Inquisition". I added some formatting to make it easier to read on this site.

____
#### Sourdough Country Loaf 

340g King Arthur Unbleached All-Purpose Flour 

100g King Arthur Unbleached All-Purpose Flour 

227g Baker's Special Dry Milk or nonfat dry milk 

9g unsweetened unsalted butter 

1 large egg 

227g shredded grated Parmesan cheese 

1 1/4 teaspoons salt 

1/2 teaspoon ground cardamom
    
Directions   

Beat together the milk, butter and Parmesan cheese in a large bowl.  Blend together the egg, milk and Parmesan cheese. Stir in the coarsely chopped Parmesan and cheese.  Beat in the melted butter, butter, milk and Parmesan, stirring constantly.  Add the wet milk, butter and Parmesan.  Pour the eggs into the prepared pan. Bake the bread for 30 to 45 minutes.  Remove the bread from the oven and cool on a rack for 5 to 10 minutes before slicing.  Remove the bread from the oven and cool to room temperature. Store the bread for about 45 days at room temperature, or freeze for up to 1 month.  
   
Tips from our bakers 

No crust-free breadsticks? Don't be tempted to try this. While it's tempting to use your favorite loaf of breadsticks for this holiday season, you won't find a suitable "No-Dry Dough" recipe for this holiday season. We recommend using a variety of loaves to make a dough that tastes quite like ours:


____
#### The Spanish Inquisition     

This bread has been made with the help of a mix and flour mixture, using just one teaspoon of the other flour.  If you're using this bread, combine all of the ingredients. The dough will become so moist that you can't see the glaze or glaze on it.  This bread should be light brown, well-rounded, and light brown. 
    
Dough  

85g King Arthur Unbleached All-Purpose Flour 

1 1/4 teaspoons sugar 

1 1/2 teaspoons vanilla extract 

25g to 35g sugar 

227g King Arthur Unbleached All-Purpose Flour 

1 1/4 teaspoons salt 
    
Directions   

To make the dough:  Mix together all the ingredients of the dough.  If using the mixer, combine all the ingredients with the ingredients. The dough will be a soft dough, not sticky.   Place the dough in a greased bowl or food processor. Pulse until smooth and elastic, about 1 hour.  Place the dough in the pan of a food processor; set the speed with a mixer.  Turn the dough out onto a lightly greased work surface. Scrape the dough from the surface of the pan and place the bottom of the pan onto a lightly greased surface.   Place the dough onto a lightly greased work surface or bread processor. Pulse until smooth and elastic.  Place the dough on a lightly greased work surface. Repeat the process until you've made a smooth, smooth dough.  Cover the dough and allow it to rise for 1 hour at room temperature.  When it's doubled, add the flour, baking powder, salt and vanilla extract and turn the dough out onto a lightly greased work surface. Transfer the dough to a lightly greased work surface, and let it rise for 1 1/2 hours, or until it's doubled in bulk. The risen dough may be kneaded for additional time, depending on the amount of water and water that you use.  Lightly grease a 10" x 12" (3" x 4") loaf pan.   Bake the bread for 45 to 60 minutes, or until it's golden brown. Remove it from the oven, and immediately remove it from the pan. Let it cool, covered, for 1 hour.  


## Hardware

I was too cheap to pay for AWS credits so I ran this on my desktop, originally built in 2011, I think I added the 3GB GPU around 2016?


## Data

A few thousand bread recipes scraped from the likes of King Arthur Flour and All-recipes I think.


___
[Back to projects page](/)


