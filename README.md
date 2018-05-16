AngularJS - How to setup a new project:
=====================================

1. app-root is the roor component. It is in ./src/app/app.component.ts
2. main.ts - starting point
3. To create a new Angular project
	ng new APP-NAME
	Ex: ng new angular-app

4. To start the APP, goto the newly created folder and execute the command
	ng serve --open
	To start in specific port, use ng serve --open --port PORT
	Ex: cd angular-app/
		ng serve --open --port 4300
		
5. To create new components
	ng generate component COMP-NAME 
	Ex: ng generate component users
	
	When the component is created, it adds a html, a css and a ts file in the folder

6. 	Two way binding
	[(ngModel)] - to bind the textbox and the value ( to and fro )

7. Any new component added has to be declared in one NgModule. In this case the app.module.ts	

8. for loop
	- *ngFor="let OBJ of OBJECT-LIST"
	Ex: *ngFor="let user of users"
	
	<li *ngFor="let user of users" (click)="onSelect(user)">

9. style declared in the @Component	will be applied only to that component. It will not be affect the outer elements.

10. Event binding
	Ex: click and select 
	(click)="onSelect(user)"
	
	TODO: Need to check why this is not working as expected. 

11. @Input 
	- a settable property. It will be set with a value when it is data bound with a property binding.

12. Constructor 
	- Max 1 constructor is allowed in a class
	- used for Dependency Injection (DI) of other module/service
	- constructor(private http: Http) {}

13. @Inject	
	- can be used for DI 
	- constructor(@Inject(Http) private http) {}
	- seems to be a manual way to do DI as Angular supports resolving dependencies from the emitted metadata (At this point, docs suggest DI using constructor is better).

14. @Injectable
	- mandatory when we define a service without which there is no way for Angular to read what dependencies it requires.		

15. ngOnInit
	- a lifecycle hook
	- gives a signal that Angular has finished initialising the component.

16. Service
	- a provider to do backend logic/access DB etc.

17. Observable
	- to asynchronously process the requests.
	- Ex: A list of users have to be fetched and displayed in the UI.
		- first the UI has to wait/hang around until it sends a request to backend server, the service fetches the users and returns a response to the UI.
		- Observable is like a publish - subscribe mechanism... 
		- when a component subscribes to it, it starts publishing objects/messages (Observable of) until the execution is completed. 
		- after the execution is completed the Angular promises come to picture.

What I understood about AngularJS so far:
=========================================
1. Basic building blocks - NgModules
2. Components
	- every app will have a root component and others for the features
	- defines class to define data, logic and combine views
	- it is a functional unit
	- it has the following
		# a selector ( the tag - ex: <user-list> )
		# template url ( the html template)
		# providers ( the service used ) 

3. Views
	- screen elements
	- a hierarchical structure that helps Angular to detect and respond to changes in the DOM
	- it is formed using templates
	
4. Services
	- provides the functionality
	
5. Template
	- combines HTML with Angular directives.
	- provides the binding (property and events)
			
6. Metadata
	- a service provides info for Dependency Injection (DI) in components
	
7. NgModule
	- provides compilation context
	- Root module - the AppModule provides the bootstrap mechanism
	- it is a container with components,services, etc
	
8. Router module
	- it is a Ngmodule that provides service to define the navigation paths in the application	
	
	
