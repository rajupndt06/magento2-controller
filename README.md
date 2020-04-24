# magento2-controller

 How to Create Controller in Magento 2

In Magento 2 Controller has one or more files in Controller folder of module, it includes actions of 

class which contain execute() method. There are 2 different controllers, they are frontend controller 

and backend controller. They are generally similar of workflow, but admin controller is a little 

different. There is a checking permission method in admin controller, it calls form key.

How controller work?

It receive an request from end-user.
For example:   http://example.com/route_name/controller/action

- route_name : It is a unique name which is set in routes.xml.
- controller : It is the folder inside Controller folder.
- action : It is a class with execute method to process request.

One of the important in Magento system is frontController (Magento\Framework\App
\FrontController), it alway receives request then route controller, action by route_name Let’s take 
an example of routing an request:

If there is an action of controller class found, execute() method will be run.

To understand more about regarding how to Create Controller in Magento 2 we will do a practice.

youtube video tutorial : https://youtu.be/BzErwqfY24Q

Lets do this practically, you need to follow step by step

Step 1: Create a new module called Techone_ControllerTutorial
- Create the namespace Techone in the path app\code.
- Create the module name ControllerTutorial in the path app\code\Techone.
- Create the file named registration.php in the path app\code\Techone\ControllerTutorial

use \Magento\Framework\Component\ComponentRegistrar;
ComponentRegistrar::register(ComponentRegistrar::MODULE, 'Techone_ControllerTutorial', 
__DIR__);

- Create the file name module.xml in the path app\code\Techone\ControllerTutorial\etc


End of step #1, I have been completed the step to create new module called 

Techone_ControllerTutorial

Step 2: Declar routes.xml file.
- To create a controller, we need to create a folder inside Controller folder of module and declare an 

action class inside it. For example, we create a index controller and a index action for module 

Techone_ControllerTutorial.
- Create the file name routes.xml in the path app\code\Techone\ControllerTutorial\etc
\frontend\routes.xml

Step 3: Declare controller file
- Create new file named Index.php in the path app\code\Techone\ControllerTutorial\Controller
\Index\Index.php


- As you see, all controllers must be extended \Magento\Framework\App\Action\Action class which 
has dispatch method which will call execute() method in action class. In this execute() method, we 
will write all of our controller logic and will return response for the request.

Step 4 : Declare Layout file
- Create new file named controllertutorial_index_index.xml in the path app\code\Techone
\ControllerTutorial\view\frontend\layout\controllertutorial_index_index.xml


Step 5: Declare Block file
- Create new file named Index.php in the path app\code\Techone\ControllerTutorial\Block
\Index.php

Step 6: Declare template file
- Create new file named index.phtml in the path app\code\Techone\ControllerTutorial\view
\frontend\templates\index.phtml

<h2>Controller created successfully</h2>

Step 7: Test and see the results
Run the command lines following:
- php bin/magento setup:upgrade 
- php bin/magento setup:static-content:deploy -f
- php bin/magento cache:flush

Let’s open browser and navigate to
http://domain.com/controllertutorial/index/index
or
http://domain.com/controllertutorial/
