# WIP Code Conventions 

- for component files: must stay consistent between file and component name, exactly the same. decide if file names are kebab case or pascal case like the component.
- always tailwind, no ccs-in-js. can consider design systems like daisy UI if appropriate. ask.
- prioritize function components and hooks over class components, unless you have a very good reason. 
- something about component abstractions 
  - small reusable ui components shared across the codebase to maintain design patterns & ui concistency. pre-convined default are set already and can be expanded. 
  - (see how it go it wrong in seaweb code)