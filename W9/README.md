Jungle notes:
1. when signup, we set sessions, but how would that make us log in directly
A: Even though you set sessions it won't let you log in directly, you still need logic to check the sessions. It is just set in our browser that you can use directly. In this case, I have logic in application.rb to check current_user
2. session[user_id] VS session[:user_id]
A: if we don't use symbol, this is lose meaning when it is out of scope
3. Why session name or key is not user_id
A: Because sessions hide the user_id for us in order not to expose it to the outside world
4. when we need to use edit, you might need to add update all the same time to dabasase otherwise it might not work
5. database interaction: bin/rails c After that you can run different command interact with database
