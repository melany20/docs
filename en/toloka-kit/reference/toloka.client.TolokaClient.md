# TolokaClient
`toloka.client.TolokaClient` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.0.post1/src/client/__init__.py#L169)

```python
TolokaClient(
    self,
    token: str,
    environment: Union[Environment, str, None] = None,
    retries: Union[int, Retry] = 3,
    timeout: Union[float, Tuple[float, float]] = 10.0,
    url: Optional[str] = None,
    retry_quotas: Union[List[str], str, None] = 'MIN',
    retryer_factory: Optional[Callable[[], Retry]] = None,
    act_under_account_id: Optional[str] = None
)
```

Class that implements interaction with [Toloka API](https://toloka.ai/en/docs/api/).


Objects of other classes are created and modified only in memory of your computer.
You can transfer information about these objects to Toloka only by calling one of the `TolokaClient` methods.

For example, creating an instance of `Project` class will not add a project to Toloka right away. It will create a `Project` instance in your local memory.
You need to call the `TolokaClient.create_project` method and pass the created project instance to it.
Likewise, if you read a project using the `TolokaClient.get_project` method, you will get an instance of `Project` class.
But if you change some parameters in this object manually in your code, it will not affect the existing project in Toloka.
Call `TolokaClient.update_project` and pass the `Project` to apply your changes.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`token`|**str**|<p>Your OAuth token for Toloka. You can learn more about how to get it [here](https://toloka.ai/en/docs/api/concepts/access#token)</p>
`environment`|**Union\[[Environment](toloka.client.TolokaClient.Environment.md), str, None\]**|<p>There are two environments in Toloka:</p> <ul> <li>`SANDBOX` – [Testing environment](https://sandbox.toloka.dev) for Toloka requesters. You can test complex projects before assigning tasks to Tolokers. Nobody will see your tasks, and it&#x27;s free.</li> <li>`PRODUCTION` – [Production environment](https://toloka.dev) for Toloka requesters. You spend money there and get the results.</li> </ul> <p>You need to register in each environment separately. OAuth tokens are generated in each environment separately too. </p><p>Default value: `None`.</p>
`retries`|**Union\[int, Retry\]**|<p>Retry policy for failed API requests. Possible values:</p> <ul> <li>`int` – The number of retries for all requests. In this case, the retry policy is created automatically.</li> <li>`Retry` object – Deprecated type. Use `retryer_factory` parameter instead.</li> </ul> <p></p><p>Default value: `3`.</p>
`timeout`|**Union\[float, Tuple\[float, float\]\]**|<p>Number of seconds that [Requests library](https://docs.python-requests.org/en/master) will wait for your client to establish connection to a remote machine. Possible values:</p> <ul> <li>`float` – Single value for both connect and read timeouts.</li> <li>`Tuple[float, float]` – Tuple sets the values for connect and read timeouts separately.</li> <li>`None` – Set the timeout to `None` only if you are willing to wait the [Response](https://docs.python-requests.org/en/master/api/#requests.Response) for unlimited number of seconds.</li> </ul> <p></p><p>Default value: `10.0`.</p>
`url`|**Optional\[str\]**|<p>Set a specific URL instead of Toloka environment. May be useful for testing purposes. You can only set one parameter – either `url` or `environment`, not both of them. </p><p>Default value: `None`.</p>
`retry_quotas`|**Union\[List\[str\], str, None\]**|<p>List of quotas that must be retried. Set `None` or pass an empty list for not retrying any quotas. If you specified the `retries` as `Retry` instance, you must set this parameter to `None`. Possible values:</p> <ul> <li>`MIN` - Retry minutes quotas.</li> <li>`HOUR` - Retry hourly quotas. This means that the program just sleeps for an hour.</li> <li>`DAY` - Retry daily quotas. We do not recommend retrying these quotas.</li> </ul> <p></p><p>Default value: `MIN`.</p>
`retryer_factory`|**Optional\[Callable\[\[\], Retry\]\]**|<p>Factory that creates `Retry` object. Fully specified retry policy that will apply to all requests. </p><p>Default value: `None`.</p>
`act_under_account_id`|**Optional\[str\]**|<p>ID of the requester that has been shared access with the current token owner account. All requests will be made using a specified account. See [Shared access to the requester&#x27;s account](https://toloka.ai/en/docs/guide/concepts/multiple-access) documentation page. ID of the requester can be retrieved using the [get_requester](toloka.client.TolokaClient.get_requester.md) method (this method should be called by the account owner using account&#x27;s token).</p>

**Examples:**

How to create `TolokaClient` instance and make your first request to Toloka.

```python
your_oauth_token = input('Enter your token:')
toloka_client = toloka.TolokaClient(your_oauth_token, 'PRODUCTION')  # Or switch to 'SANDBOX' environment
```

{% note info %}

`toloka_client` instance will be used to pass all API calls later on.

{% endnote %}
## Methods Summary

| Method | Description |
| :------| :-----------|
[accept_assignment](toloka.client.TolokaClient.accept_assignment.md)| Accepts an assignment.
[add_message_thread_to_folders](toloka.client.TolokaClient.add_message_thread_to_folders.md)| Adds a message chain to one or more folders ("unread", "important" etc.)
[aggregate_solutions_by_pool](toloka.client.TolokaClient.aggregate_solutions_by_pool.md)| Starts aggregation of responses in all completed tasks in a pool.
[aggregate_solutions_by_task](toloka.client.TolokaClient.aggregate_solutions_by_task.md)| Aggregates responses to a single task on the Toloka server.
[archive_app_project](toloka.client.TolokaClient.archive_app_project.md)| Archives an App project.
[archive_pool](toloka.client.TolokaClient.archive_pool.md)| Sends pool to archive
[archive_pool_async](toloka.client.TolokaClient.archive_pool_async.md)| Sends pool to archive, asynchronous version
[archive_project](toloka.client.TolokaClient.archive_project.md)| Sends project to archive
[archive_project_async](toloka.client.TolokaClient.archive_project_async.md)| Sends project to archive, asynchronous version
[archive_training](toloka.client.TolokaClient.archive_training.md)| Sends training to archive
[archive_training_async](toloka.client.TolokaClient.archive_training_async.md)| Sends training to archive, asynchronous version
[clone_pool](toloka.client.TolokaClient.clone_pool.md)| Duplicates existing pool
[clone_pool_async](toloka.client.TolokaClient.clone_pool_async.md)| Duplicates existing pool, asynchronous version
[clone_project](toloka.client.TolokaClient.clone_project.md)| Synchronously clones the project, all pools and trainings
[clone_training](toloka.client.TolokaClient.clone_training.md)| Duplicates existing training
[clone_training_async](toloka.client.TolokaClient.clone_training_async.md)| Duplicates existing training, asynchronous version
[close_pool](toloka.client.TolokaClient.close_pool.md)| Stops distributing tasks from the pool
[close_pool_async](toloka.client.TolokaClient.close_pool_async.md)| Stops distributing tasks from the pool, asynchronous version
[close_pool_for_update](toloka.client.TolokaClient.close_pool_for_update.md)| Closes pool for update
[close_pool_for_update_async](toloka.client.TolokaClient.close_pool_for_update_async.md)| Closes pool for update, asynchronous version
[close_training](toloka.client.TolokaClient.close_training.md)| Stops distributing tasks from the training
[close_training_async](toloka.client.TolokaClient.close_training_async.md)| Stops distributing tasks from the training, asynchronous version
[compose_message_thread](toloka.client.TolokaClient.compose_message_thread.md)| Sends a message to a Toloker.
[create_app_batch](toloka.client.TolokaClient.create_app_batch.md)| Creates a batch with task items in an App project in Toloka.
[create_app_item](toloka.client.TolokaClient.create_app_item.md)| Creates an App task item in Toloka.
[create_app_items](toloka.client.TolokaClient.create_app_items.md)| Creates task items in an App project in Toloka and adds them to an existing batch.
[create_app_project](toloka.client.TolokaClient.create_app_project.md)| Creates an App project in Toloka.
[create_pool](toloka.client.TolokaClient.create_pool.md)| Creates a new pool
[create_project](toloka.client.TolokaClient.create_project.md)| Creates a new project
[create_skill](toloka.client.TolokaClient.create_skill.md)| Creates a new Skill
[create_task](toloka.client.TolokaClient.create_task.md)| Creates a new task in Toloka.
[create_task_suite](toloka.client.TolokaClient.create_task_suite.md)| Creates a task suite in Toloka.
[create_task_suites](toloka.client.TolokaClient.create_task_suites.md)| Creates several task suites in Toloka.
[create_task_suites_async](toloka.client.TolokaClient.create_task_suites_async.md)| Creates several task suites in Toloka asynchronously.
[create_tasks](toloka.client.TolokaClient.create_tasks.md)| Creates several tasks in Toloka.
[create_tasks_async](toloka.client.TolokaClient.create_tasks_async.md)| Creates tasks in Toloka asynchronously.
[create_training](toloka.client.TolokaClient.create_training.md)| Creates a new training
[create_user_bonus](toloka.client.TolokaClient.create_user_bonus.md)| Issues payments directly to a Toloker.
[create_user_bonuses](toloka.client.TolokaClient.create_user_bonuses.md)| Creates rewards for Tolokers.
[create_user_bonuses_async](toloka.client.TolokaClient.create_user_bonuses_async.md)| Issues payments directly to Tolokers, asynchronously creates many `UserBonus` instances.
[delete_user_restriction](toloka.client.TolokaClient.delete_user_restriction.md)| Unlocks existing restriction
[delete_user_skill](toloka.client.TolokaClient.delete_user_skill.md)| Drop specific UserSkill
[delete_webhook_subscription](toloka.client.TolokaClient.delete_webhook_subscription.md)| Drop specific webhook-subscription
[download_attachment](toloka.client.TolokaClient.download_attachment.md)| Downloads specific attachment
[find_aggregated_solutions](toloka.client.TolokaClient.find_aggregated_solutions.md)| Finds aggregated responses that match certain criteria.
[find_app_batches](toloka.client.TolokaClient.find_app_batches.md)| Finds batches that match certain criteria in an App project.
[find_app_items](toloka.client.TolokaClient.find_app_items.md)| Finds task items that match certain criteria in an App project.
[find_app_projects](toloka.client.TolokaClient.find_app_projects.md)| Finds App projects that match certain criteria.
[find_apps](toloka.client.TolokaClient.find_apps.md)| Finds App solutions that match certain criteria.
[find_assignments](toloka.client.TolokaClient.find_assignments.md)| Finds assignments that match certain criteria.
[find_attachments](toloka.client.TolokaClient.find_attachments.md)| Finds attachments that match certain criteria and returns their metadata.
[find_message_threads](toloka.client.TolokaClient.find_message_threads.md)| Finds message threads that match certain criteria.
[find_operations](toloka.client.TolokaClient.find_operations.md)| Finds operations that match certain criteria.
[find_pools](toloka.client.TolokaClient.find_pools.md)| Finds pools that match certain criteria.
[find_projects](toloka.client.TolokaClient.find_projects.md)| Finds projects that match certain criteria.
[find_skills](toloka.client.TolokaClient.find_skills.md)| Finds skills that match certain criteria.
[find_task_suites](toloka.client.TolokaClient.find_task_suites.md)| Finds task suites that match certain criteria.
[find_tasks](toloka.client.TolokaClient.find_tasks.md)| Finds tasks that match certain criteria.
[find_trainings](toloka.client.TolokaClient.find_trainings.md)| Finds training pools that match certain criteria.
[find_user_bonuses](toloka.client.TolokaClient.find_user_bonuses.md)| Finds Tolokers' rewards that match certain criteria.
[find_user_restrictions](toloka.client.TolokaClient.find_user_restrictions.md)| Finds Toloker restrictions that match certain criteria.
[find_user_skills](toloka.client.TolokaClient.find_user_skills.md)| Finds Toloker's skills that match certain criteria.
[find_webhook_subscriptions](toloka.client.TolokaClient.find_webhook_subscriptions.md)| Finds webhook subscriptions that match certain criteria.
[get_aggregated_solutions](toloka.client.TolokaClient.get_aggregated_solutions.md)| Finds all aggregated responses that match certain criteria.
[get_analytics](toloka.client.TolokaClient.get_analytics.md)| Sends analytics queries, for example, to estimate the percentage of completed tasks in the pool
[get_app](toloka.client.TolokaClient.get_app.md)| Gets information from Toloka about an App solution.
[get_app_batch](toloka.client.TolokaClient.get_app_batch.md)| Gets information from Toloka about a batch in an App project.
[get_app_batches](toloka.client.TolokaClient.get_app_batches.md)| Finds all batches that match certain criteria in an App project.
[get_app_item](toloka.client.TolokaClient.get_app_item.md)| Gets information from Toloka about an App task item.
[get_app_items](toloka.client.TolokaClient.get_app_items.md)| Finds all App task items that match certain criteria in an App project.
[get_app_project](toloka.client.TolokaClient.get_app_project.md)| Gets information from Toloka about an App project.
[get_app_projects](toloka.client.TolokaClient.get_app_projects.md)| Finds all App projects that match certain criteria.
[get_apps](toloka.client.TolokaClient.get_apps.md)| Finds all App solutions that match certain criteria.
[get_assignment](toloka.client.TolokaClient.get_assignment.md)| Gets an assignment from Toloka.
[get_assignments](toloka.client.TolokaClient.get_assignments.md)| Finds all assignments that match certain criteria.
[get_assignments_df](toloka.client.TolokaClient.get_assignments_df.md)| Downloads assignments as pandas.DataFrame.
[get_attachment](toloka.client.TolokaClient.get_attachment.md)| Gets attachment metadata without downloading it
[get_attachments](toloka.client.TolokaClient.get_attachments.md)| Finds all attachments that match certain criteria and returns their metadata.
[get_message_threads](toloka.client.TolokaClient.get_message_threads.md)| Finds all message threads that match certain criteria.
[get_operation](toloka.client.TolokaClient.get_operation.md)| Reads information about operation
[get_operation_log](toloka.client.TolokaClient.get_operation_log.md)| Reads information about validation errors and which task (or task suites) were created
[get_operations](toloka.client.TolokaClient.get_operations.md)| Finds all operations that match certain rules and returns them in an iterable object
[get_pool](toloka.client.TolokaClient.get_pool.md)| Reads one specific pool
[get_pools](toloka.client.TolokaClient.get_pools.md)| Finds all pools that match certain criteria.
[get_project](toloka.client.TolokaClient.get_project.md)| Reads one specific project
[get_projects](toloka.client.TolokaClient.get_projects.md)| Finds all projects that match certain criteria.
[get_requester](toloka.client.TolokaClient.get_requester.md)| Reads information about the customer and the account balance
[get_skill](toloka.client.TolokaClient.get_skill.md)| Reads one specific skill
[get_skills](toloka.client.TolokaClient.get_skills.md)| Finds all skills that match certain criteria.
[get_task](toloka.client.TolokaClient.get_task.md)| Gets a task with specified ID from Toloka.
[get_task_suite](toloka.client.TolokaClient.get_task_suite.md)| Reads one task suite.
[get_task_suites](toloka.client.TolokaClient.get_task_suites.md)| Finds all task suites that match certain criteria.
[get_tasks](toloka.client.TolokaClient.get_tasks.md)| Finds all tasks that match certain criteria.
[get_training](toloka.client.TolokaClient.get_training.md)| Reads one specific training
[get_trainings](toloka.client.TolokaClient.get_trainings.md)| Finds all training pools that match certain criteria.
[get_user](toloka.client.TolokaClient.get_user.md)| Gets Toloker metadata by `user_id`.
[get_user_bonus](toloka.client.TolokaClient.get_user_bonus.md)| Gets information about a Toloker's reward.
[get_user_bonuses](toloka.client.TolokaClient.get_user_bonuses.md)| Finds all Tolokers' rewards that match certain rules and returns them in an iterable object
[get_user_restriction](toloka.client.TolokaClient.get_user_restriction.md)| Gets information about a Toloker restriction.
[get_user_restrictions](toloka.client.TolokaClient.get_user_restrictions.md)| Finds all Toloker restrictions that match certain criteria.
[get_user_skill](toloka.client.TolokaClient.get_user_skill.md)| Gets the value of a Toloker's skill
[get_user_skills](toloka.client.TolokaClient.get_user_skills.md)| Finds all Toloker's skills that match certain criteria.
[get_webhook_subscription](toloka.client.TolokaClient.get_webhook_subscription.md)| Get one specific webhook-subscription
[get_webhook_subscriptions](toloka.client.TolokaClient.get_webhook_subscriptions.md)| Finds all webhook subscriptions that match certain criteria.
[open_pool](toloka.client.TolokaClient.open_pool.md)| Starts distributing tasks from the pool
[open_pool_async](toloka.client.TolokaClient.open_pool_async.md)| Starts distributing tasks from the pool, asynchronous version
[open_training](toloka.client.TolokaClient.open_training.md)| Starts distributing tasks from the training
[open_training_async](toloka.client.TolokaClient.open_training_async.md)| Starts distributing tasks from the training, asynchronous version
[patch_app_batch](toloka.client.TolokaClient.patch_app_batch.md)| Updates an App batch name.
[patch_assignment](toloka.client.TolokaClient.patch_assignment.md)| Changes an assignment status and associated public comment.
[patch_pool](toloka.client.TolokaClient.patch_pool.md)| Changes the priority of the pool issue
[patch_task](toloka.client.TolokaClient.patch_task.md)| Changes a task overlap value.
[patch_task_overlap_or_min](toloka.client.TolokaClient.patch_task_overlap_or_min.md)| Stops assigning a task to Tolokers.
[patch_task_suite](toloka.client.TolokaClient.patch_task_suite.md)| Changes task suite parameter values in Toloka.
[patch_task_suite_overlap_or_min](toloka.client.TolokaClient.patch_task_suite_overlap_or_min.md)| Stops issuing the task suites
[reject_assignment](toloka.client.TolokaClient.reject_assignment.md)| Rejects an assignment.
[remove_message_thread_from_folders](toloka.client.TolokaClient.remove_message_thread_from_folders.md)| Deletes a message chain from one or more folders ("unread", "important" etc.)
[reply_message_thread](toloka.client.TolokaClient.reply_message_thread.md)| Replies to a message in thread
[resume_app_batch](toloka.client.TolokaClient.resume_app_batch.md)| Resumes annotation of a batch of task items in an App project.
[set_user_restriction](toloka.client.TolokaClient.set_user_restriction.md)| Restricts access to projects or pools for a Toloker.
[set_user_skill](toloka.client.TolokaClient.set_user_skill.md)| Assigns a skill to a Toloker.
[start_app_batch](toloka.client.TolokaClient.start_app_batch.md)| Launches annotation of a batch of task items in an App project.
[stop_app_batch](toloka.client.TolokaClient.stop_app_batch.md)| Stops annotation of a batch of task items in an App project.
[unarchive_app_project](toloka.client.TolokaClient.unarchive_app_project.md)| Unarchives an App project.
[update_pool](toloka.client.TolokaClient.update_pool.md)| Makes changes to the pool
[update_project](toloka.client.TolokaClient.update_project.md)| Makes changes to the project
[update_skill](toloka.client.TolokaClient.update_skill.md)| Makes changes to the skill
[update_training](toloka.client.TolokaClient.update_training.md)| Makes changes to the training
[upsert_webhook_subscriptions](toloka.client.TolokaClient.upsert_webhook_subscriptions.md)| Creates (upsert) many webhook-subscriptions.
[wait_operation](toloka.client.TolokaClient.wait_operation.md)| Waits for the operation to complete, and return it
