# week3examReview
Answering questions after week 3 exam


- What is a Fragment? Usage? Ways to add?

Fragmets are used as an extension of ui/activity. They can be added as a <fragment> tag or they can be inflated into a ViewGroup in the activity's layout.

- How do we communicate between fragments?

Communicating between fragment and an activity could be done through an interface which the activity would implement and in return the fragment could call the method on the activity. The reference to which should be overidden in the onAttach() event in Fragment.

- How to remove all fragments added to an activity?

You would have to save the tags for every fragment in the Activity and then remove Fragments using FragmentManager by tag.

- How to pass data to the fragment while initializing?

You add the data to a Bundle which you would pass to a fragment instance using setArguments() method.

- How to save the state of the fragment on rotation?

Using  setRetainInstance() method

- What is a broadcast reciever? Ways to register?

A BroadcastReceiver is one of the Android components used to receive System or Application events. Receivers could be registered in Manifest in older version of android or in the context of the Activity in the onStart() and onStop() events.

- What are some restrictions on BR on the newer versions?

In devices running android 9 or later NETWORK_STATE_CHANGED_ACTION will not receive information about user's location or any personal information.

- How do we secure the scope of broadcast?

Using persmissions we could set who can receive broadcasts.	

- How to add permission while sending broadcasts?

Add permission string as the second argument in sendBroadcast() method	

- What is a service? What are the types?

A service is an android component that is responsible for performing long running tasks in the background. Services are of types: Background, Foreground and Bound.	

- What is the difference between a intentservice/service?

IntentService runs on a separate thread by default and all the tasks will be implemented in a Queue by default	

- How does bound service communicates? Ways

Using a Binder class, Messenger or AIDL.

- How to implement the communication using Binder?

You create a Binder subclass in BoundService which passes the reference to service in one of its methods. In the activity you can implement the ServiceConnection interface to get the reference to the service in onServiceConnected() method. Use bindService() and unbindService() in onStart() and onStop() events.	

- Resrtrictions on the background services for new versions?

In the new versions if your app is not in the foreground, the running services will be terminated. It is encouraged to use JobScheduler to do long lasting tasks in the background.	

- What is a job scheduler? Why do we need to use it?

JobScheduler is used to schedule tasks at a later time even if your app is not running. It is used similarly to Service.

- How do we schedule a job using the job scheduler?

You create a JobInfo object to hold the data about the conditions under which it would start your task. Then using the WorkManager/JobScheduler you schedule the job with your tasks.	

- What are some criteria we can set for the JobInfo?

Some of the criteria would be a time delay, time interval, connectivity status, battery status. battery lifetime status etc.	

- What is the permission required for a JobService?

android.permission.BIND_JOB_SERVICE 

- Why do we need an architecture for the app?

To separate different types of logic for different components of the application. To create order within the codebase.

- What does Low Couping and High Cohesion mean?

Low coupling means that different modules should not depend on each  other. High cohesion means within the modules the logic should be only about what module is about, for example database connector should not be altering the views in the activity.

- What is the differrent between MVC and MVP?

In the MVC the view does not have any logic. Whereas in MVP the view has logic which contains the UI events etc.

- How do we implement MVP? Classes? Data flow?

We create a BaseView and BasePresenter interfaces. Then for the RandomActivity we create a RandomContract class which will hold View interface extending BaseView and Presenter interface extending  BasePresenter. RandomActivity would implement RandomContract.View and RandomPresenter class would implement RandomContract.Presenter. RandomContract interfaces should hold the list of methods which is how the activity and the presenter send events back and forth. On starting activity, we should bind the view to the presenter.

- What is the different between a LinkedList and Arraylist?

LinkedList links the items in the list, whereas arraylist just recreates the array. Getting the element is faster in the ArrayList whereas putting element and removing element is faster in LinkedList.

- What is the different between HashMap and HashTable?

HashTable is syncronized and does not allow null keys or null values.

- How does the garbage collector work?

When the object no longer has any reference to it throughout the code, it will be destroyed. Uses mark and sweep algorithm. Goes through every object declared and marks it as used, the rest is marked as garbage and space is freed up.

