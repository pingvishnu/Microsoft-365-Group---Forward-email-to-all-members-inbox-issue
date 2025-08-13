# Microsoft-365-Group---Forward-email-to-all-members-inbox-issue
Microsoft 365 Group - forwarding emails to all member inbox doesn't work 

# To check if a Microsoft 365 Group (GroupMailbox) allows external senders, use:


Get-UnifiedGroup -Identity "xyz@domain.com" | Format-List DisplayName,PrimarySmtpAddress,AutoSubscribeNewMembers


AutoSubscribeNewMembers = True →  New members receive emails in their inbox

AutoSubscribeNewMembers = False → Members must manually check the group inbox (emails not copied to personal inbox)

#To Enable "Send copy to members" for new members

You can enable it with this PowerShell command:


Set-UnifiedGroup -Identity "xyz@domain.com" -AutoSubscribeNewMembers $true



#Important Notes:

This setting only affects users added after this change.

Existing members won't be subscribed automatically unless they:

Manually enable it in Outlook (Follow in Inbox) or remove the members from group in admin center and add back. 




