---
layout: post
title: "Final: Anime/Manga-Style Filter with PoseNet and Style Transfer"
categories: mlforweb
---

![alt text](/images/mlforweb/final/steps.png)
I made a selfie filter that adjusts a photo in the browser with [style transfer](https://ml5js.org/docs/StyleTransfer){:target="_blank"} and [poseNet](https://ml5js.org/docs/PoseNet){:target="_blank"} models with [ml5](https://ml5js.org/){:target="_blank"}. The filter mimicks the art style in anime and manga (Japanese animation and comics), transforming a photo of the user to a character in a comic. Similar to filter apps like Meitu, the webpage will take in a user's photo, process it, and then allow them to download it.

<blockquote class="instagram-media" data-instgrm-permalink="https://www.instagram.com/p/BPXu1crgd_W/?utm_source=ig_embed&amp;utm_medium=loading" data-instgrm-version="12" style=" background:#FFF; border:0; border-radius:3px; box-shadow:0 0 1px 0 rgba(0,0,0,0.5),0 1px 10px 0 rgba(0,0,0,0.15); margin: 1px; max-width:540px; min-width:326px; padding:0; width:99.375%; width:-webkit-calc(100% - 2px); width:calc(100% - 2px);"><div style="padding:16px;"> <a href="https://www.instagram.com/p/BPXu1crgd_W/?utm_source=ig_embed&amp;utm_medium=loading" style=" background:#FFFFFF; line-height:0; padding:0 0; text-align:center; text-decoration:none; width:100%;" target="_blank"> <div style=" display: flex; flex-direction: row; align-items: center;"> <div style="background-color: #F4F4F4; border-radius: 50%; flex-grow: 0; height: 40px; margin-right: 14px; width: 40px;"></div> <div style="display: flex; flex-direction: column; flex-grow: 1; justify-content: center;"> <div style=" background-color: #F4F4F4; border-radius: 4px; flex-grow: 0; height: 14px; margin-bottom: 6px; width: 100px;"></div> <div style=" background-color: #F4F4F4; border-radius: 4px; flex-grow: 0; height: 14px; width: 60px;"></div></div></div><div style="padding: 19% 0;"></div><div style="display:block; height:50px; margin:0 auto 12px; width:50px;"><svg width="50px" height="50px" viewBox="0 0 60 60" version="1.1" xmlns="https://www.w3.org/2000/svg" xmlns:xlink="https://www.w3.org/1999/xlink"><g stroke="none" stroke-width="1" fill="none" fill-rule="evenodd"><g transform="translate(-511.000000, -20.000000)" fill="#000000"><g><path d="M556.869,30.41 C554.814,30.41 553.148,32.076 553.148,34.131 C553.148,36.186 554.814,37.852 556.869,37.852 C558.924,37.852 560.59,36.186 560.59,34.131 C560.59,32.076 558.924,30.41 556.869,30.41 M541,60.657 C535.114,60.657 530.342,55.887 530.342,50 C530.342,44.114 535.114,39.342 541,39.342 C546.887,39.342 551.658,44.114 551.658,50 C551.658,55.887 546.887,60.657 541,60.657 M541,33.886 C532.1,33.886 524.886,41.1 524.886,50 C524.886,58.899 532.1,66.113 541,66.113 C549.9,66.113 557.115,58.899 557.115,50 C557.115,41.1 549.9,33.886 541,33.886 M565.378,62.101 C565.244,65.022 564.756,66.606 564.346,67.663 C563.803,69.06 563.154,70.057 562.106,71.106 C561.058,72.155 560.06,72.803 558.662,73.347 C557.607,73.757 556.021,74.244 553.102,74.378 C549.944,74.521 548.997,74.552 541,74.552 C533.003,74.552 532.056,74.521 528.898,74.378 C525.979,74.244 524.393,73.757 523.338,73.347 C521.94,72.803 520.942,72.155 519.894,71.106 C518.846,70.057 518.197,69.06 517.654,67.663 C517.244,66.606 516.755,65.022 516.623,62.101 C516.479,58.943 516.448,57.996 516.448,50 C516.448,42.003 516.479,41.056 516.623,37.899 C516.755,34.978 517.244,33.391 517.654,32.338 C518.197,30.938 518.846,29.942 519.894,28.894 C520.942,27.846 521.94,27.196 523.338,26.654 C524.393,26.244 525.979,25.756 528.898,25.623 C532.057,25.479 533.004,25.448 541,25.448 C548.997,25.448 549.943,25.479 553.102,25.623 C556.021,25.756 557.607,26.244 558.662,26.654 C560.06,27.196 561.058,27.846 562.106,28.894 C563.154,29.942 563.803,30.938 564.346,32.338 C564.756,33.391 565.244,34.978 565.378,37.899 C565.522,41.056 565.552,42.003 565.552,50 C565.552,57.996 565.522,58.943 565.378,62.101 M570.82,37.631 C570.674,34.438 570.167,32.258 569.425,30.349 C568.659,28.377 567.633,26.702 565.965,25.035 C564.297,23.368 562.623,22.342 560.652,21.575 C558.743,20.834 556.562,20.326 553.369,20.18 C550.169,20.033 549.148,20 541,20 C532.853,20 531.831,20.033 528.631,20.18 C525.438,20.326 523.257,20.834 521.349,21.575 C519.376,22.342 517.703,23.368 516.035,25.035 C514.368,26.702 513.342,28.377 512.574,30.349 C511.834,32.258 511.326,34.438 511.181,37.631 C511.035,40.831 511,41.851 511,50 C511,58.147 511.035,59.17 511.181,62.369 C511.326,65.562 511.834,67.743 512.574,69.651 C513.342,71.625 514.368,73.296 516.035,74.965 C517.703,76.634 519.376,77.658 521.349,78.425 C523.257,79.167 525.438,79.673 528.631,79.82 C531.831,79.965 532.853,80.001 541,80.001 C549.148,80.001 550.169,79.965 553.369,79.82 C556.562,79.673 558.743,79.167 560.652,78.425 C562.623,77.658 564.297,76.634 565.965,74.965 C567.633,73.296 568.659,71.625 569.425,69.651 C570.167,67.743 570.674,65.562 570.82,62.369 C570.966,59.17 571,58.147 571,50 C571,41.851 570.966,40.831 570.82,37.631"></path></g></g></g></svg></div><div style="padding-top: 8px;"> <div style=" color:#3897f0; font-family:Arial,sans-serif; font-size:14px; font-style:normal; font-weight:550; line-height:18px;"> View this post on Instagram</div></div><div style="padding: 12.5% 0;"></div> <div style="display: flex; flex-direction: row; margin-bottom: 14px; align-items: center;"><div> <div style="background-color: #F4F4F4; border-radius: 50%; height: 12.5px; width: 12.5px; transform: translateX(0px) translateY(7px);"></div> <div style="background-color: #F4F4F4; height: 12.5px; transform: rotate(-45deg) translateX(3px) translateY(1px); width: 12.5px; flex-grow: 0; margin-right: 14px; margin-left: 2px;"></div> <div style="background-color: #F4F4F4; border-radius: 50%; height: 12.5px; width: 12.5px; transform: translateX(9px) translateY(-18px);"></div></div><div style="margin-left: 8px;"> <div style=" background-color: #F4F4F4; border-radius: 50%; flex-grow: 0; height: 20px; width: 20px;"></div> <div style=" width: 0; height: 0; border-top: 2px solid transparent; border-left: 6px solid #f4f4f4; border-bottom: 2px solid transparent; transform: translateX(16px) translateY(-4px) rotate(30deg)"></div></div><div style="margin-left: auto;"> <div style=" width: 0px; border-top: 8px solid #F4F4F4; border-right: 8px solid transparent; transform: translateY(16px);"></div> <div style=" background-color: #F4F4F4; flex-grow: 0; height: 12px; width: 16px; transform: translateY(-4px);"></div> <div style=" width: 0; height: 0; border-top: 8px solid #F4F4F4; border-left: 8px solid transparent; transform: translateY(-4px) translateX(8px);"></div></div></div> <div style="display: flex; flex-direction: column; flex-grow: 1; justify-content: center; margin-bottom: 24px;"> <div style=" background-color: #F4F4F4; border-radius: 4px; flex-grow: 0; height: 14px; margin-bottom: 6px; width: 224px;"></div> <div style=" background-color: #F4F4F4; border-radius: 4px; flex-grow: 0; height: 14px; width: 144px;"></div></div></a><p style=" color:#c9c8cd; font-family:Arial,sans-serif; font-size:14px; line-height:17px; margin-bottom:0; margin-top:8px; overflow:hidden; padding:8px 0 7px; text-align:center; text-overflow:ellipsis; white-space:nowrap;"><a href="https://www.instagram.com/p/BPXu1crgd_W/?utm_source=ig_embed&amp;utm_medium=loading" style=" color:#c9c8cd; font-family:Arial,sans-serif; font-size:14px; font-style:normal; font-weight:normal; line-height:17px; text-decoration:none;" target="_blank">A post shared by Jane Douglas (@penny_dreadful)</a> on <time style=" font-family:Arial,sans-serif; font-size:14px; line-height:17px;" datetime="2017-01-17T15:38:56+00:00">Jan 17, 2017 at 7:38am PST</time></p></div></blockquote> <script async src="//www.instagram.com/embed.js"></script>

### Style Transfer ###

First, I tested different models of style transfer to find one that would best give an 'anime style' to a photo. I wasn't sure how different styles of anime drawings would translate to style transfer models so I tried different types of 'anime style' depictions. I think the first one gave the best result although I like the 4th one too.
I used [this method](https://github.com/yining1023/styleTransfer_spell){:target="_blank"} to train a style transfer model remotely with Spell and convert to ml5.

![alt text](https://github.com/jirrian/jirrian.github.io/blob/master/images/mlforweb/final/styletransfer_test_matrix.png?raw=true)

As you can see, style transfer doesn't change the size and shape of the face. So even if the drawings have exaggerated eyes, the style transfer model won't. Yining, my teacher, suggested I use poseNet to enlarge the eyes and add other elements. I photoshopped the original photo with the effects I wanted to test how they would look like after being style transfered.

### Pose Net ###

I used poseNet with ml5 to detect the eyes and nose of the person in the photo. I then used those points to relatively enlarge the eyes and place blush and sparkles. I started using poseNet on a webcam video stream to test and then moved to an [image input](https://github.com/ml5js/ml5-examples/tree/master/p5js/PoseNet/PoseNet_image_single){:target="_blank"}.
![alt text](/images/mlforweb/final/posenet_test.png)

![alt text](/images/mlforweb/final/posenet_keypoints.png)
![alt text](/images/mlforweb/final/posenet_keypoints_eyes.png)
![alt text](/images/mlforweb/final/posenet_eyes.png)

The blush are ellipses drawn relative to the eyes and nose keypoints. The sparkles are just a transparent png image.
![alt text](/images/mlforweb/final/posenet_blush_test.png)
![alt text](/images/mlforweb/final/posenet_sparkles.png)

I then saved frames of the canvas and created an image of the first frame. I fed that image into the style transfer model to get the final result.
![alt text](/images/mlforweb/final/final.png)

The results are a big scary. Mainly because of the rough edges of the enlarge eyes. I would like to use p5.mask with a radial gradient circle image instead of just drawing an ellipse in the future to blend the layers better.

### Testing ###

I tested with another image of myself to see if the results would be comparable. The original image must be 500 by 500 pixels right now.
![alt text](/images/mlforweb/final/me2_500.jpg)
![alt text](/images/mlforweb/final/test_result1.png)
![alt text](/images/mlforweb/final/test_result2.png)

It works the same as the first image I tried but it's still scary.

### Edit 12/18/18: Improvements ###

I worked on other aspects of this filter for [another class](http://blog.jzhong.today/computationaltypo/Final-Filter-With-Manga-Text/) and was able to improve the blending aroud the eyes with a png mask file.
![alt text](/images/mlforweb/final/filter2.png)

My final results as of now with different style transfer models:
![alt text](/images/mlforweb/final/final_2_style1.png)
![alt text](/images/mlforweb/final/final_2_style2.png)

It works with more than 1 pose too if you change the poseNet function call from `poseNet.singlePose(img);` to `poseNet.multiPose(img);`.
![alt text](/images/mlforweb/final/final_2_style1_2pose.png)
![alt text](/images/mlforweb/final/final_2_style2_2poses.png)

### To Do ###

Originally, I also wanted to use body-pix to detect the silhouette of the figure and remove the background but I ran out of time. This is so I can have the filtered person in the original photo-realistic environment or just replace the background with something else completely.

Photoshopped idea of what I was going for:
![alt text](/images/mlforweb/final/proposed_final.png)

Most importatnly, I want people to upload a photo and then be able to download it. The user interface needs to be built. I would also like them to be able to choose between single pose or multiple poses and different style transfer models.

One issue I thought of is that this model probably won't work well for people with darker skin tones. This is a similar issue that the Meitu app had too. Maybe I will need to use a different type of style transfer or experiment with parameters so that the colors of the style are not applied as strongly.

### Links ###

[Link to project github repo](https://github.com/jirrian/anime_filter){:target="_blank"}

[Try the demo here](http://jzhong.today/anime_filter/){:target="_blank"}

[PoseNet single pose image example](https://github.com/ml5js/ml5-examples/tree/master/p5js/PoseNet/PoseNet_image_single){:target="_blank"}

[Fast style transfer with Spell and ml5 tutorial](https://github.com/yining1023/styleTransfer_spell){:target="_blank"}

[Blog post on typography part of filter (in progress)](http://blog.jzhong.today/computationaltypo/Final-Filter-With-Manga-Text/){:target="_blank"}
