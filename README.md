# slack-notifier
Integrate WP app with slack.com (Slack Auth - Create Channel - Fetch All Workspace Channels)
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
                                  # Plugin Creation Algorithm
                                ---------------------------
1- Create New Folder Called slack-notifier in the wp-content/plugins/
----------------------------------------------------------------------------------------------------------------------------
2- Create the main php file for the plugin in the created dir and name it as slack-notifier.php
----------------------------------------------------------------------------------------------------------------------------
3- Create Your Header Comment
----------------------------------------------------------------------------------------------------------------------------
4- Create Custom MetaBox -(to prevent user from key insertion..only value will be inserted)- using :

   * the key is slack_api_key
   * the value given from slack app
   * wporg_add_custom_box()
   * add_action('add_meta_boxes','wporg_add_custom_box')
   * save_post()
   
----------------------------------------------------------------------------------------------------------------------------   
5- register the past functions in register_activation_hook() to appear for user after plugin activated
----------------------------------------------------------------------------------------------------------------------------
6- create the function for fetching data from the slack called 'fetching_slack_data()'
----------------------------------------------------------------------------------------------------------------------------
7- choose the proper action for the hook to fire this function from the following :

   * add-action('init','fetching_slack_data')
   * add-action('plugin_loaded','fetching_slack_data')
   * add-action('admin_notices','fetching_slack_data')
   
----------------------------------------------------------------------------------------------------------------------------   
* we may use : add_short_code() do_short_code()
----------------------------------------------------------------------------------------------------------------------------
8- if you create options file use :

   * update_option()
   * get_option()
   * delete_option()
   
----------------------------------------------------------------------------------------------------------------------------   
9- Create function to uninstalling the plugin to remove the data from DB using this hook register_activation_hook()
----------------------------------------------------------------------------------------------------------------------------
10-Create function for deactivation of the plugin using this hook register_deactivation_hook()
   
