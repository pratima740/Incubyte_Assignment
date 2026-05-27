# Incubyte_Assignment
Feature: Gmail Compose Functionality

Scenario: Send email successfully
Given user is logged into Gmail
When user clicks on Compose button
And enters valid recipient email
And enters subject "Incubyte"
And enters body "QA test for Incubyte"
And clicks Send
Then email should be sent successfully

Scenario: Validate mandatory recipient field
Given user opens compose window
When user leaves recipient field empty
And clicks Send
Then validation error should appear

Scenario: Validate invalid email address
Given user opens compose window
When user enters invalid email format
Then Gmail should show invalid email error

Scenario: Verify draft auto save
Given user is composing email
When user closes compose popup without sending
Then email draft should be auto-saved

Scenario: Verify attachment upload
Given user opens compose window
When user uploads a valid attachment
Then attachment should upload successfully

Scenario: Verify oversized attachment restriction
Given user opens compose window
When user uploads attachment larger than 25MB
Then Gmail should show attachment size warning

Scenario: Verify undo send option
Given user sends an email
When user clicks Undo option
Then sent email should be reverted

Scenario: Verify CC functionality
Given user opens compose window
When user adds recipient in CC
And sends email
Then CC recipient should receive email

Scenario: Verify BCC functionality
Given user opens compose window
When user adds recipient in BCC
And sends email
Then BCC recipient should receive email

Scenario: Verify empty subject warning
Given user enters recipient and body
When user leaves subject empty
And clicks Send
Then Gmail should display missing subject warning

Scenario: Prevent duplicate email sending
Given user composes an email
When user clicks Send button multiple times rapidly
Then only one email should be sent

Scenario: Recover draft after browser crash
Given user is composing an email
When browser crashes unexpectedly
Then draft should recover after reopening Gmail

Scenario: Validate invalid pasted email list
Given user opens compose window
When user pastes invalid email addresses
Then Gmail should highlight invalid emails

Scenario: Verify attachment upload cancellation
Given user uploads an attachment
When user cancels upload midway
Then attachment upload should stop successfully

Scenario: Verify send email to self
Given user enters own Gmail address
When user sends email
Then email should deliver successfully

Scenario: Verify draft synchronization across tabs
Given Gmail is opened in multiple tabs
When draft is updated in one tab
Then changes should sync in other tabs

Scenario: Verify special Unicode characters support
Given user enters Unicode characters in email body
When email is sent
Then recipient should receive proper characters

Scenario: Verify send during attachment upload
Given attachment upload is in progress
When user clicks Send
Then Gmail should complete upload or warn user

Scenario: Verify autosave during network interruption
Given user is drafting email
When internet disconnects temporarily
Then Gmail should retry saving draft automatically

Scenario: Verify high zoom accessibility
Given browser zoom is set to 200%
When user opens compose window
Then compose functionality should remain usable
