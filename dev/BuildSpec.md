This is a placeholder for the .md you will build in your GPT Project (or claude, whoever). 

Keep the initial build to 3 phases

    - You'll have WAY more of it already mapped out but...
      - The agent doesn't need to know that. 
      - You'll learn things in the initial phases that will likely have you adjusting where to go next. 
  
    - once you get over three... an agent will often start recommending breaking it up into sub-phases... 4a,  5a, b, c and so on. And you start to veer down specific paths before attending to more foundational things, or just dragging out the initial build , burning tokens. 

    - Get the core features, schema & shell built first, go from there. 
    - Do LARGE changes via future buildspec.md files, small tweeks via prompts. 




RECOMMENDED FEATURES to include in the core app. 
- A debug log 
- A active "update" checker, so users are alerted to updates. 
  - One simple example is an active update checker that works by having the app periodically download a small public latest.json file in your 'main' repo that lists the newest available version. It compares that version to the version built into the user’s installed app, then shows a notice if an update is available. It does not update the app automatically or run system commands; it only tells the user what command to run manually. This means also that your app will need to have it's latest version info baked into the metadata. So be sure to update that metadata each time to push a release. 