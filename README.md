
**Steps**
- Check that this project has environment variables whenever you see:
    ```
     proccess.env.PORT
    ```
- Create a mongodb account on cloud - Atlas

- Configure Secrets on repository level such as MONGODB_USERNAME and MONGODB_PASSWORD

   Path to Repo level secrets: Go to your Github > select your repo > settings > Secrets  and variables > Actions > Repository secrets

- On deployment.yml set Mongo db (Username and Password) info using secrets defined previously

- To create Environment variables:
    1- Create an Environment. ex: "Testing"
    2- Add Environment secret to this Environment such as MONGODB_USERNAME and MONGODB_PASSWORD
    3- On Job level, above *job name* add prop `environment` with value 'testing'

**In Summary:**
- Learn diferent syntax of accessing variables:
    - environment variables ( workflow, job or step level) accessed by 
    ```
        ${{ env.MONGODB_DB_NAME }}
       //or
        $MONGODB_DB_NAME
    ```
    - secrets (repository level or via Environments) accessed by 
    ```
        ${{  secrets.MONGODB_PASSWORD}}
    ```
    - Environments secrets - that are secrets specific for an environment

