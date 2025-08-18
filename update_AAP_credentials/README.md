# How this playbook works?
1. It will retrieve all credentials with 'Source Control' label from AAP
2. It will pull creds from CCP
3. Do data cleaning, data manipulation to obtain updated_users list
4. Update AAP git credentials with updated_users

# When to trigger this workflow?
- Triggered via API call to AAP, this playbook will be stored locally on controller
- Trigger via F5 when primary Git server goes down, and trigger again after it is restored
# extra_vars to be passed during execution


| Variable                          | Description                                                                  |
| --------------------------------- | -----------------------------------------------------------------------------|
| `AAP_IP`                          | IP address of Ansible Automation Platform, example `aap-server1`             |
| `AAP_TOKEN`                       | Authentication token for AAP                                                 |
| `GIT_SERVER`                      | Either `GIT1` or `GIT2`                                                      |
| `CYBERARK_CCP_URL`                | URL of CyberArk CCP, example `ccp-server1`                                   |
| `CYBERARK_CCP_CREDS_LIST_TO_PULL` | List of credential names to pull from CyberArk CCP, example `gitlab-user1`   |
