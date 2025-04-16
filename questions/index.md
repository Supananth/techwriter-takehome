

### How do you revert a change from one branch and add it to another?
Scenario: You make an update and commit to the `master` branch. Afterward, you realize that you should've made this 
change to another branch named `staging`. What do you do? 
### Answer: 
To revert a change from the `master` branch and add it to the `staging` branch:

1. **Switch to the `staging` branch:**
   ```bash
   git checkout staging
   ```

2. **Select the commit from the `master` branch:**
   - Find the commit hash of the change made in the `master` branch:
     ```bash
     git log master
     ```
   - Apply that commit to the `staging` branch:
     ```bash
     git cherry-pick <commit-hash>
     ```

3. **Remove the commit from the `master` branch:**
   - To revert the change, navigate back to the `master` branch:
     ```bash
     git checkout master
     ```
   - Undo the specified commit:
     ```bash
     git revert <commit-hash>
     ```
The change is now present in the `staging` branch and reverted in the `master` branch.

### How do you squash git commits?
Scenario: You have a GitHub branch with 5 separate commits. What is the command line sequence to squash those 5 commits 
into a single commit?

### Answer:
To squash the last five Git commits into a single commit:

1. **Start an interactive rebase:**
   If your last 5 commits need to be squashed, run:
   ```bash
   git rebase -i HEAD~5
   ```

2. **Mark commits to be squashed:**
   - An interactive editor opens displaying the last 5 commits.
   - For the first commit, leave the word `pick` as it is.
   - For the remaining 4 commits, change `pick` to `squash`.

   For example:
   ```
   pick <commit-hash-1> Commit message 1
   squash <commit-hash-2> Commit message 2
   squash <commit-hash-3> Commit message 3
   squash <commit-hash-4> Commit message 4
   squash <commit-hash-5> Commit message 5
   ```

3. **Complete the rebase:**
   Save and close the editor for Git to squash the commits into a single file.

5. **Resolve conflicts (if any):**
   Git notifies you of merge conflicts, if any. Resolve the conflicts and continue the rebase:
   ```bash
   git rebase --continue
   ```

6. **Confirm the changes:**
   To confirm your changes have been squashed into a single commit, run:
   ```bash
   git log
   ```

Your last five commits are now combined into a single commit.

### What is wrong with this sample JSON syntax?

```
{
  "first_name" : "Franz",
  "last_name" : "Kafka",
  "location" : "San Francisco"
  "streams" : true,
  "kafka" : 2.3 
}
```
### Answer: 
The provided JSON syntax has a missing comma between key-value pairs. After `"San Francisco"`, the `"location"` key-value pair is not separated by a comma.

**Correct format:**
   ```
{
  "first_name" : "Franz",
  "last_name" : "Kafka",
  "location" : "San Francisco",
  "streams" : true,
  "kafka" : 2.3 
}
```

### What is the Kafka broker port?

Scenario: Complete step 1 of [this Confluent Platform quick start](https://docs.confluent.io/platform/current/get-started/platform-quickstart.html) to 
install a local version of Confluent Platform. After completing step 1, what port number is the broker running on?

### Answer: 

### What are the default topics created when you install Confluent Platform using the quick start?

Scenario: After you complete step 1 of [this quick start](https://docs.confluent.io/platform/current/get-started/platform-quickstart.html), 
open Control Center at http://localhost:9021/. What are the names of the default topics that are created by Kafka?
### Answer: 

### What is the name of the Connect cluster that is created?

Scenario: Complete step 2 of [this quick start](https://docs.confluent.io/platform/current/get-started/platform-quickstart.html). 
What is the name of the Connect cluster that is created?

### Answer: 

****
