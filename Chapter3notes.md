# django_project

1. Create a new app:  
       python manage.py startapp  rango(appName)
       
2. Tell Django the existence of this app:
       add app name (rango) in django_project---setting.py----INSTALLED_APPS

3. Now we can create a new view method in rango--Views.py:
   from django.http import HttpResponse
       // index is the method name.        🧐:still don't understand what does request mean? an object of HttpResponse???? 
       ref index(request):               
           return HttpResponse("the thing u want to add")
            
4. Map this View (index,about or whatever the method name) // give a URL to it so that other can access
       URL ☞  Uniform Resource Locater  
       
       4.1 in the django_project---urls.py---urlpatterns list add:
            url(r'^$', views.index, name='index')  
            /**
              * "r" means raw data. 
              * "^" means begin with
              * "$" mean end up with
       🧐     * "^$" together here means for all the urlpatterns??? still unclear
              * this basically means for all the url we go to view.index method and display that view.
              */
       4.1 in in the django_project---urls.py---urlpatterns list add:
            url(r'^rango/', include('rango.urls')),
            // for url if we find "rango/" then go to rango app. (rango.urls) . 
                   this job is handled by: from django.conf.urls import url
