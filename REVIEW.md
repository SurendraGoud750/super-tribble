1) SQL injection 
  file name:- events_controller.rb
  line - 10, 21
  category: sql injection
  buisness impact: Haker may pass the valid sql queries along with the params attributes, so it can be delete our existing tables and due to that our application will not be working and getting errors.

2) N+1 query found
  file name:- events_controller.rb
  line - 33, 36
  category: N+1 query
  buisness impact: Here for each event we are feching user and other required data because we did not egar load associated data with the event query, it can be slow our sql query and frequently run sql query.

3) manully build JSON for index and show action
   filename: events-controller.rb
   line - 23
   category:- Hard to maintain, FAT controller
   solution: we can use Jbuilder, fast_jsonapi gem

4) Code repeated:
   filename - events_controllers.rb
   line - 49, show and destroy method
   category: code redundency 
   

5) Performence issue:
   filename - events_controllers.rb
   line - 23
   category: performence issue 
   buisness impact: what if we have 10000 events, slow api
   solution: we can use pagination to avoide slow api.

6) Missing error:
   filename - events_controllers.rb
   line - 90,49
   category: performence issue 
   buisness impact: if event not found then -- app will crash
   solution: We can use begin and rescue to catch proper error handling.

7) Auth is missing:
   filename - events_controllers.rb
   line - 89,48
   category: authorization issue 
   buisness impact: anyone logged-in user can perform opration for this critical action
   solution: we can use before_action call back to prevent those action and verify it only event owner can perform to update or delete thier events instead of other user.




