# IIS 10 MVC 401 / 401.3 Error


  https://stackoverflow.com/questions/19162553/iis-401-3-unauthorized

   I have struggled on this same issue for several days. It can be solved by modifying the security user access properties of the file system folder on which your site is mapped. But IIS_IUSRS is not the only account you must authorize.

   In IIS management console, in the Authentication part of the configuration of your site, modify the "Anonymous authentication" line and check the account set as "Specific user" (mine is IUSR).
   Give read and execution permission on the folder of your site to the account listed as the specific user.
   OR

   In IIS management console, in the Authentication part of the configuration of your site, modify the "Anonymous authentication" line by selecting "Identity of the application pool" instead of "Specific user".

### If Using Azure AD:

    Turn off Windows Authentication
  
    Turn ON Anonymous Authentication
