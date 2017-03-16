# Docker Utils

Tools and Utils for Docker and Amazon ECS (EC2 Container Service).

## run-local-task.py
This tool converts an **ECS Task Definition** into a `docker run` command. It supports all available options in Task Definition except _volumesFrom_. All settings will be converted to appropriate `docker run` arguments.

Command line:
```
run-local-task.py [--profile AWS_CREDENTIALS_PROFILE] [--container CONTAINER_DEFINITION_NAME] TASK_DEFINITION_NAME
```

**--profile**  name of the AWS credentials profile from _~/.aws/credentials_ file. If not set, default profile will be used. More about the profile configuration can be found here: http://docs.aws.amazon.com/cli/latest/userguide/cli-chap-getting-started.html#cli-config-files

**--container** the tool will pickup first container in the Task Definition. If a Task Definition has more than one container defined, container name should be specified.

**TASK_DEFINITION_NAME** can be either a name or an _ARN_. If the revision number is not provided, latest active revision will be used.
