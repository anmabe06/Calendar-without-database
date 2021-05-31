# Calendar-without-database
Code by anmabe06

This is a program that works like a calendar. The calendar is reseted after every time the user stops it from running.

This is a step by step guide on how to do it:
  1. Create an array to store all of the events:
      ```
      eventList = []
     
  2. Create a prototype object for all of the events:
      ```
      function event(title, startDate, endDate){
        this.Title = title;
        this.StartDate = new Date(startDate);
        this.EndDate = new Date(endDate);
      }
    
  3. Make a function for event creation:
      ```
      function createNewEvent(){
        console.log("\n######################## NEW EVENT ########################");

        title = prompt("#  EVENT TITLE: ")
        startDate = prompt("#  START DATE: ");
        endDate = prompt("#  END DATE: ");
        console.log("###########################################################\n\n");
        newEvent = new event(title, startDate, endDate);

        if(newEvent.StartDate != "Invalid Date"){
          eventList.push(newEvent);

        }else{
          console.log("\n\n\n\nERROR: introduce the date with the following format: 'YYYY/MM/DD HH:MinMin:SS:MsMs'\n")
        }
        setup();
      }

  
  4. Make a function to show all of the events in a user-friendly style:
      ```
      function showEvents(){
        if(eventList.length == 0){
          console.log("\nALERT: You need to add an event first!\n")
          setup();

        }else{
          console.log("\n##################### SHOWING EVENTS #####################")
          for(i = 0; i < eventList.length; i++){
            console.log("#  EVENT: " + eventList[i].Title + "\n#  START DATE: " + eventList[i].StartDate + "\n#  END DATE: " + eventList[i].EndDate);
            console.log("##############");
          }
          console.log("##########################################################");
        }
      }
  
  5. Create a starting function that interacts with the user:
      ```
      function setup(){
        input = prompt("What would you like to do?\nSee events [1]\nCreate new event [2]\n>>>")
        input = parseInt(input);

        if(input == 1){
          showEvents();

        }else if(input == 2){
          createNewEvent(eventList);

        }else{
          console.log("\nPlease, introduce 1 or 2");
          setup();
        }
      }
  
  7. Call the starting function, and start planning your holydays!
      ```
      setup();
