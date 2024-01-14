1. Dowload the patch to be applied.
2. Open SQL Server Configuration Manager. SQL Server, Integration Services, and Analysis Services should be in the same state, either all running or all stopped.
**Note:** If SQL Server is running but Analysis Services is stopped, errors may occur during the patch process.
**Note:** Although not always necessary, a Windows restart may be required before the installation.
**Note:** Each instance should be installed separately, and operations should not be performed by selecting all instances simultaneously.
3. Check the version before the patch:
~~~sql
select @@SERVERNAME, @@VERSION, SERVICENAME
~~~
4. Run the setup file as an administrator.
5. Follow the steps, but it should be remembered that only one instance should be patched at a time.
6. Check the version after the patch.