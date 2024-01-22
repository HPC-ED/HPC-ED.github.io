# Instructions on how to add events/posts

## Instructions

1. Log into the HPC-ED/[HPC-ED.github.io](http://hpc-ed.github.io/) Github Repo
2. Ensure in the “main” branch
3. Go to _posts directory
4. Duplicate one of the current posts
5. Rename the file with the format of YYYY-MM-DD-name-of-event.md
6. Edit the file front matter with the appropriate text. Unused items can be removed or commented out with a leading hash mark (#). All front matter lines with the exception of abstract mush begin on the far left of the front matter area without any spaces per the yaml format requirements. 
    - layout: This sets the default layout template of the page. For posts it should always be set as post.
    
    ```jsx
    layout: post
    ```
    
    - title: “Name of the Event”
    - dateofevent: date time and time zone of the event in the format YYYY-MM-DD HH:MM:SS timezone
    - categories: Tags for the type of event such as paper, workshop, hackathon, panel, etc.
    - presenters: This item can take multiple entries using the below format
    
    ```jsx
    presenters:
    - Presenter One
    - Presenter Two
    ```
    
    - location: Geographical location
    - eventurl: Website of the event at host event  and/or registration link
    - associated_event: This item can be used to link to the main site of a host conference or event using the below array item format.
    
    ```jsx
    associated_event: ["Name of Conference", "https://conference.url"]
    ```
    
    - author: This item can accept multiple entries using the below format
    
    ```jsx
    author:
    - Author One
    - Author Two
    ```
    
    - abstract: Due to the lengthy nature of an abstract this item can use the > sign after the item to then allow a multiline amount of text.
    
    ```jsx
    abstract: >
      Insert all the text you need
    for your abstract over
    multiple lines as 
    needed
    ```
    
    - files: Multiple files can be added to this item using an array format. Note the name of the file on the site will be generated based on the file name. Downloadable files should be added to the downloads/presentations directory in the site directories
    
    ```jsx
    files: 
    - "downloads/presentations/Lastname-PresentationName1-event.pdf"
    - "downloads/presentations/Lastname-PresentationName2-event.pdf"
    ```
    
    - image: Images should be added to the downloads/photos directory of the site and then link provided
    
    ```jsx
    image: "downloads/photos/personname-event.jpeg"
    ```
    
    - image_description: This image description is used both for captions and alt-txt for images
    - hide: This item when set as true allows a post to be hidden
    
    ```jsx
    hide: true
    ```
    
    - If there is content after the - - -  of the front matter, click on the post will display in post view, otherwise the “eventurl” item link with be utilized. This was done to account for future events that may not have additional information for an actual post page. This can be forced by adding a HTML comment.
    
    ```jsx
    ---
    layout: post
    ...
    ---
    <!-- Added this to have post link on listing instead of host event (in front matter as "eventurl" ) link -->
    ```
    
    ## Example Post
    
    ```jsx
    ---
    layout: post
    title:  "[SC23] Tenth SC Workshop on Best Practices for HPC Training and Education"
    dateofevent:   2023-11-13 14:00:00 -0600
    categories: workshop
    presenters: 
    - Susan Mehringer
    location: "Denver, Colorado"
    eventurl: https://sc23.conference-program.com/presentation/?id=ws_bphpcte108&sess=sess456
    author: 
    - Susan Mehringer
    - Mary P. Thomas
    - Kate Cahill
    - Charlie Dey
    - David Joiner
    - Richard Knepper
    - John-Paul Navarro
    - Jeaime H. Powell
    abstract: >
      Throughout the cyberinfrastructure community there is a large range of resources available to train faculty and young scholars about successful utilization of computational resources for research. The challenge that the community faces is that training materials abound, but they can be difficult to find, and often have little information about the quality or relevance of offerings. Building on existing software technology, we propose to build a way for the community to better share and find training and education materials, through a federated training repository. In this scenario, organizations and authors retain physical and legal ownership of their materials by sharing only catalog information, organizations can refine local portals to use the best and most appropriate materials from both local and remote sources, and learners can take advantage of materials that are reviewed and described more clearly.
    associated_event: ["Supercomputing 23", "https://sc23.supercomputing.org"]
    files: ["downloads/presentations/Mehringer-ScalingHPCEducation-SC23.pdf"] 
    image: "downloads/photos/Mehringer_SC23.jpeg"
    image_description: "Photo of Susan Mehringer giving the presentation at SC23."
    ---
    <!-- Added this to have post link on listing instead of host event (in front matter as "eventurl" ) link -->
    ```
    
    ## Example Hidden Post