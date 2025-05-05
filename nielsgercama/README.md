To make your own compendium site, take the following step:

0. Create a folder. The name of the folder is what your site will be called.

1. Create your compendium pdf.

    a. Keep in mind that the ratio of most PC screens is 16:9. The optimal ratio for your compendium should thus be something around that value.

    b. You can deviate in page size however! Feel free to make some pages wider or longer. The site will automatically adjust so that viewers can scroll to see the content. 

    c. On pages where you want to embed something like a video, please do make a page for it in the compendium. Say you want to just embed a miro board on page 5 of your compendium, then leave page 5 in the pdf file blank. It will become the background to that page.

    d. Save the compendium pdf in the site folder. Call it "compendium.pdf"

2. Create a folder called "media".

    a. Drop the files you want to embed in this folder.
    
    b. For videos and 3d models, its possible to add a so-called "poster". This will serve as a placeholder while your embedded video or model loads. This can be any .jpg image. Just drop your poster with the other media in the "media" folder. 

3. Create a file called "map.js"

    a. This file will tell my code where your media is located, and on what page to load which media.
    
    b. Add the information in the following format (you can copy paste this and edit what you need):

```javascript
const PAGES = {
    3 : {

        type : "youtube", //video, youtube, miro , 3d 
        link:"https://www.youtube.com/watch?v=Bx3O0N2nXcs&t=3s",
        posterlink:""

    },

    4 : {

        type:"video", //video, youtube, miro , 3d 
        link:"media/examplevideo/video.mp4",
        posterlink:"media/examplevideo/poster.jpg",

    },
    
    6 : {

        type:"miro", //video, youtube, miro , 3d 
        link:"https://miro.com/app/embed/uXjVKE-Zstg=/?pres=1&frameId=3458764614711847583&embedId=503370172447&autoplay=yep",
        posterlink:""

	},

    7 : {

        type:"3d", //video, youtube, miro , 3d 
        link:"media/example3d/model.glb",
        posterlink:"media/example3d/poster.jpg"

    }

}

const AUDIO = {

    "media/exampleaudio/audio2.mp3" : {

        "start" : 2,
        "end" : 5

    }
}
```

To embed media on a page simply add the page number as seen above and specify the media "type" (this can be either "video", "youtube", "miro" or "3d"). Give a link to the media. Video files must be .mp4, 3d models must be .glb. To embed a miro board or youtube video, simply paste the url to the board in the "link" section.

In the above example, I am embedding a video on page 4, a miro board on page 6 and a 3d model on page 7. Notice that each time, in the "link" section, I provide a link to where the file is stored. I do this as well for the poster, for the video and 3d example. You can leave the "posterlink" section empty (like this: "") if you're not using posters. Miro boards don't need posters, so there we leave posterlink blank. 

For the audio, there is a separate section. In this example, I added the link to my first audio file. I then tell the code that the file should start playing on page 2, and end on page 5. Audio format must be .mp3


[OPTIONAL] Finally, you are able to change the design of the digital compendium buttons. Inside your "media" folder, create another folder called "page". 

Make sure your image has a transparent background and is saved as a .png file if you want this.

1. For the loading page icon, add a png image (minimum 512 px by 512 px) called "loading.png" inside the "page" folder.
2. If you want, you can also change the icon shown on the tab of your browser. This should be a .ico image (max. 256 px by 256 px). 
3. Change the next page button by placing a .png image in the "page" folder called "next.png" (max. 512px by 512 px) 
4. Change the previous page button by placing a .png image in the "page" folder called "previous.png" (max. 512px by 512 px) 
5. For pages which require scrolling down, a flashing image will appear onscreen indicating that the page continues below. You can change the look of this image by placing a .png image in the "page" folder called "down.png". If you don't want this image, you can add a completely transparent .png image. Either way, max. 512 px by 512 px again. 


