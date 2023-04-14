To run the project go to steps:
1- git clone  https://github.com/enghesham/crud_task.git
2- composer update
3- copy .env.example and paste it in the file root and rename it .env
4- php artisan key:generate
5- php artisan migrate
6- npm install
7- npm run dev
8- php artisan serve

 * add fake data using tinker
php artisan ti 
App\Models\Contact::factory(10)->create();


![ezgif com-video-to-gif](https://user-images.githubusercontent.com/66676671/232153471-3b3493ca-ad89-4bf8-9aee-4fd84711705c.gif)
