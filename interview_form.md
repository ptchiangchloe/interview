Hi Matt,

Yes, I have a lot of experience using RESTful services and some of them are with AngularJS.

Here are examples that I use AngularFireJS in conjunction with Angular.

angularfire info:
https://github.com/firebase/angularfire

Github link:
https://github.com/ptchiangchloe/Meet-Up-Event-Planner/blob/master/app/contacts/contacts.js

Here are some snippets of the conjunction:

    $scope.addContact = function() {
        var usersRef = ref.child($scope.event_name);
        console.log('adding contact...' + usersRef);
        new Promise(function(resolve) {
          usersRef.set({
              event_type: $scope.event_type,
              event_host: $scope.event_host,
              start_time: $scope.add_start_time.toString().slice(0,11),
              end_time: $scope.add_end_time.toString().slice(0,11),
              location: $scope.location
          });
          resolve();
        })
        .then(function(){
            // var id = ref.key.$id;
            console.log('It\'s a promise');

        });
        $scope.event_name = "";
        $scope.event_type = "";
        $scope.event_host = "";
        $scope.add_start_time = "";
        $scope.add_end_time = "";
        $scope.location = "";
    }

<!-- gap     -->

    $scope.editEvent = function(event) {
        var id = $scope.id;
        console.log(id);

        var record = $scope.events.$getRecord(id);
        console.log(record);
        record.event_name = $scope.event_name;
        record.event_type = $scope.event_type;
        record.event_host = $scope.event_host;
        record.start_time = $scope.edit_start_time;
        record.end_time = $scope.edit_end_time;
        record.location = $scope.location;
        //save
        $scope.events.$save(record).then(function(ref) {
            console.log(ref.key);
        });

        $scope.event_name = "";
        $scope.event_type = "";
        $scope.event_host = "";
        $scope.edit_start_time = "";
        $scope.edit_end_time = "";
        $scope.location = "";

        $scope.addFormShow = true;
        $scope.editFormShow = false;

    };

 As you know I've used other RESTful Api for my Neighborhood Map project such as Google Api and Foursquare Api by using AJAX and Vanilla JS.

Here is the link: https://github.com/ptchiangchloe/Neighborhood_Map/blob/master/js/map.js

And I also have some experience with Ruby on Rails full stack development which is involving representational state transfer.

Here is the link:
https://github.com/ptchiangchloe/Bloccit/blob/master/app/controllers/posts_controller.rb

Cheers

Hanyu 
