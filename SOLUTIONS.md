1. `TasksController` and `create`
2. `UsersController` and `index`
3. Step 1: the web browser issues a request for the `task/new` URL
    Step 2: Rails routes to the `task/new` to the `new` action in `TasksController`
    Step 3: `Task/new` runs `Task.inilialize` that runs the `Tasks` base class 
    Step 4: `tasks/new.html.erb` is rendered
4. `ActiveRecord::Base`
5. 1. `Index`, `GET`, displays all 
    2. `Show`, `GET`, displays whats at the certain `id` choosen
    3. `New`, `GET`, creates a new thing
    4. `Edit`, `GET`, edits what's given at the certain `id` choosen
    5. `Create`, `POST`, creates the new thing with created at time stamp
    6. `Update`, `PUT`(PATCH), updates the id choosen with updated at time stamp
    7. `Destroy`, `DELETE`, deletes the certain id

## Step Four - Use Rails Console to Create a User
first_user = User.create
   (0.0ms)  begin transaction
  User Create (1.5ms)  INSERT INTO "users" ("created_at", "updated_at") VALUES (?, ?)  [["created_at", "2019-08-14 22:08:00.203506"], ["updated_at", "2019-08-14 22:08:00.203506"]]
   (0.8ms)  commit transaction
=> #<User id: 2, email: nil, active: nil, created_at: "2019-08-14 22:08:00", updated_at: "2019-08-14 22:08:00">
>> first_user.update(email: "joe@example.com")
   (0.0ms)  begin transaction
  User Update (0.3ms)  UPDATE "users" SET "email" = ?, "updated_at" = ? WHERE "users"."id" = ?  [["email", "joe@example.com"], ["updated_at", "2019-08-14 22:08:44.278068"], ["id", 2]]
   (0.7ms)  commit transaction
=> true
>> User.first
  User Load (0.2ms)  SELECT  "users".* FROM "users" ORDER BY "users"."id" ASC LIMIT ?  [["LIMIT", 1]]
=> #<User id: 1, email: "johndoe@example.com", active: true, created_at: "2019-08-14 21:41:10", updated_at: "2019-08-14 21:41:10">
>> second_user = User.create
   (0.0ms)  begin transaction
  User Create (0.3ms)  INSERT INTO "users" ("created_at", "updated_at") VALUES (?, ?)  [["created_at", "2019-08-14 22:09:30.562074"], ["updated_at", "2019-08-14 22:09:30.562074"]]
   (0.7ms)  commit transaction
=> #<User id: 3, email: nil, active: nil, created_at: "2019-08-14 22:09:30", updated_at: "2019-08-14 22:09:30">
>> second_user.update(email: "john@example.com")
   (0.0ms)  begin transaction
  User Update (0.2ms)  UPDATE "users" SET "email" = ?, "updated_at" = ? WHERE "users"."id" = ?  [["email", "john@example.com"], ["updated_at", "2019-08-14 22:09:56.864186"], ["id", 3]]
   (0.7ms)  commit transaction
=> true
>> User.second 
  User Load (0.2ms)  SELECT  "users".* FROM "users" ORDER BY "users"."id" ASC LIMIT ? OFFSET ?  [["LIMIT", 1], ["OFFSET", 1]]
=> #<User id: 2, email: "joe@example.com", active: nil, created_at: "2019-08-14 22:08:00", updated_at: "2019-08-14 22:08:44">
>> User.third
  User Load (0.1ms)  SELECT  "users".* FROM "users" ORDER BY "users"."id" ASC LIMIT ? OFFSET ?  [["LIMIT", 1], ["OFFSET", 2]]
=> #<User id: 3, email: "john@example.com", active: nil, created_at: "2019-08-14 22:09:30", updated_at: "2019-08-14 22:09:56">