Considering the 4 hours available for the task, I have decided to organize the tests into 2 groups:
        ◦ UI Tests: Interact with each and every visual element.
        ◦ Functional Tests: Apply black box, white box, and gray box (as appropriate) to validate the application's functionality.

##Test Plan
#UI Tests
    • UI-001
        ◦ Name: Value "None" in the "Collection profile" field
        ◦ Description: The software should not generate a log report if the "Collection profile" field contains the value "None."
        ◦ Input Data: Collection profile = "None"
        ◦ Output Data: Informational message
        ◦ Expected Result: Alert indicating the impossibility of generating the report.
        ◦ Result Obtained: The "ESET Log Collector" window is displayed, including the message "No artifacts are selected."
        ◦ Status: PASSED
        ◦ Bugs: N/A

    • UI-002
        ◦ Name: Value "" in the "Save archive as" field
        ◦ Description: The software should not generate a log report if the "Save archive as" field contains the value "" (empty).
        ◦ Input Data: Save archive as = ""
        ◦ Output Data: Informational message
        ◦ Expected Result: Alert indicating the impossibility of generating the report.
        ◦ Result Obtained: The "ESET Log Collector" window is displayed, including the message "Destination name cannot be empty."
        ◦ Status: PASSED
        ◦ Bugs: N/A

    • UI-003
        ◦ Name: Help Button (?)
        ◦ Description: The software should open a new tab in the browser with the link: (https://help.eset.com/elc/4.9/en-US/)
        ◦ Input Data: Click on the Help button (?)
        ◦ Output Data: New tab opened in the browser with the link: (https://help.eset.com/elc/4.9/en-US/)
        ◦ Expected Result: The browser opens a tab with the link: (https://help.eset.com/elc/4.9/en-US/)
        ◦ Result Obtained: The browser tab opens correctly with the correct link: (https://help.eset.com/elc/4.9/en-US/)
        ◦ Status: PASSED
        ◦ Bugs: N/A

    • UI-004
        ◦ Name: Test checkboxes
        ◦ Description: The software should allow selecting and deselecting checkboxes in the "Objects to collect" and "Protect archive with password" fields.
        ◦ Input Data: Click on checkboxes
        ◦ Output Data: Checkbox selection and deselection
        ◦ Expected Result: Checkboxes should be selectable and deselectable with a single click.
        ◦ Result Obtained: Checkboxes allow selection and deselection with a single click.
        ◦ Status: *PASSED*
        ◦ Bugs: N/A

    • UI-005
        ◦ Name: Test dropdowns
        ◦ Description: The software should allow selecting various options in dropdown menus.
        ◦ Input Data: Different options within the dropdown
        ◦ Output Data: Change in the dropdown value to the selected value.
        ◦ Expected Result: The selected value should remain fixed in the input field.
        ◦ Result Obtained: The selected value remains fixed in the input field.
        ◦ Status: *PASSED*
        ◦ Bugs: N/A

    • UI-006
        ◦ Name: Test input and (...) output path button
        ◦ Description: Clicking the button should allow selecting the output path, or you can manually enter it in the input field.
        ◦ Input Data: Click on the (...) button | Manually enter the path in the input field
        ◦ Output Data: Change in the input field according to the selection or manual entry.
        ◦ Expected Result: The selected or manually entered value should remain fixed in the input field.
        ◦ Result Obtained: The selected or entered value remains fixed in the input field.
        ◦ Status: PASSED
        ◦ Bugs: N/A

    • UI-007:
        ◦ Name: Edit text in the "Operation log" field **SHOULD NOT HAPPEN**
#Functional Tests
    • FUN-001:
        ◦ Name: Select "Protect archive by password" checkbox *USING INCORRECT PASSWORD*
        ◦ Steps:
            ▪ Step 1: Define the output path
            ▪ Step 2: Click on "Protect archive by password"
            ▪ Step 3: Verify the (i) icon
            ▪ Step 4: Take note of the 'infected' password for decompressing the file
            ▪ Step 5: Click the Collect button and wait for the process to complete.
            ▪ Step 6: Decompress the file
            ▪ Step 7: Enter 'detcefni' as the password for decompression
        ◦ *FAILED*

    • FUN-002:
        ◦ Name: Select "Protect archive by password" checkbox *USING CORRECT PASSWORD*
        ◦ Steps:
            ▪ Step 1: Define the output path
            ▪ Step 2: Click on "Protect archive by password"
            ▪ Step 3: Verify the (i) icon
            ▪ Step 4: Take note of the 'infected' password for decompressing the file
            ▪ Step 5: Click the Collect button and wait for the process to complete.
            ▪ Step 6: Decompress the file
            ▪ Step 7: Enter 'infected' as the password for decompression
        ◦ *PASSED*

    • FUN-003:
        ◦ Name: Value "Default" in the "Collection profile" field
        ◦ Steps:
            ▪ Step 1: Define the output path
            ▪ Step 2: Click the Collect button and wait for the process to complete.
            ▪ Step 3: Decompress the file
        ◦ *PASSED*

    • FUN-004:
        ◦ Name: Value "Personalized" in the "Collection profile" field
        ◦ Steps:
            ▪ Step 1: Check the checkboxes to be collected
            ▪ Step 2: Define the output path
            ▪ Step 3: Click the Collect button and wait for the process to complete.
            ▪ Step 4: Decompress the file
        ◦ *PASSED*

    • FUN-005:
        ◦ Name: Value "threat detection" in the "Collection profile" field
        ◦ Steps:
            ▪ Step 1: Select the value "threat detection" in the "Collection profile" field
            ▪ Step 2: Define the output path
            ▪ Step 3: Click the Collect button and wait for the process to complete.
            ▪ Step 4: Decompress the file
        ◦ *FAILED*

    • BUG-001:
    • FUN-005 Description: The software asks for the output path again when it has already been specified in the "Save archive as" field. Steps:
        ◦ Steps to reproduce:
            ▪ Step 1: Select the value "threat detection" in the "Collection profile" field
            ▪ Step 2: Define the output path
            ▪ Step 3: Click the Collect button and wait for the process to complete.
            ▪ Step 4: Decompress the file Expected: It should not ask for the output path again since it is specified in the "Save archive as" field. Obtained result: It asks for the output path between step 3 and step 4.
    • FUN-006:
        ◦ Name: Value "threat detection" in the "Collection profile" field
        ◦ Steps:
            ▪ Step 1: Select the value "threat detection" in the "Collection profile" field
            ▪ Step 2: Define the output path
            ▪ Step 3: Click the Collect button
            ▪ Step 4: Decompress the file
        ◦ *FAILED*

    • BUG-002:
    • FUN-006 Description: The software asks for the output path again when it has already been specified in the "Save archive as" field. Steps:
        ◦ Steps to reproduce:
            ▪ Step 1: Select the value "threat detection" in the "Collection profile" field
            ▪ Step 2: Define the output path
            ▪ Step 3: Click the Collect button and wait for the process to complete.
            ▪ Step 4: Decompress the file Expected: It should not ask for the output path again since it is specified in the "Save archive as" field. Obtained result: It asks for the output path between step 3 and step 4.

    • FUN-007:
        ◦ Name: Value "1," "5," "30," or "60" in the "Recorded age limit [days]" field
        ◦ Steps:
            ▪ Step 1: Define the desired record age limit
            ▪ Step 2: Define the output path.
            ▪ Step 3: Click the Collect button and wait for the process to complete.
            ▪ Step 4: Decompress the file
            ▪ Step 5: Verify that the collected data corresponds to the selected age limit.
        ◦ *PASSED*

    • FUN-008:
        ◦ Name: Value "Original Binary from Disk" or "Filtered Binary" in the "ESET Log Collection Mode" field
        ◦ Steps:
            ▪ Step 1: Define the log collection mode.
            ▪ Step 2: Define the output path.
            ▪ Step 3: Click the Collect button and wait for the process to complete.
            ▪ Step 4: Decompress the file.
            ▪ Step 5: Verify that the collected data corresponds to the selected collection mode.
        ◦ *PASSED*

    • FUN-009: Description: Cancel the collection using the Cancel button, which appears superimposed on the Collect button while collecting.
        ◦ Step 1: Start the Collection by clicking the Collect button.
        ◦ Step 2: Cancel the Collection by clicking the Cancel button.
        ◦ Step 3: Confirm in the pop-up window that you want to cancel the collection.
        ◦ *PASSED*



