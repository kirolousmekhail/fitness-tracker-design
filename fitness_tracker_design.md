Software Design: Campus Fitness & Activity Tracker
2. IPO Chart (Input - Process - Output)
Input	Processing	Output
main_choice (Integer: 1–4)	Initialize total_cardio = 0 and total_strength = 0. Display the main menu. Validate that main_choice is between 1 and 4. Loop the main menu until the user enters 4.	Main menu and invalid-choice warning messages
cardio_choice (Integer: 1–3)	Display the Cardio submenu. Validate that cardio_choice is between 1 and 3. Map the choice to Running / Jogging, Cycling, or Swimming.	Cardio menu and selected activity
duration (Integer: ≥ 0)	Prompt for workout duration. Validate that duration is greater than or equal to 0. Add the valid duration to total_cardio.	Invalid duration warning or successful cardio confirmation
strength_choice (Integer: 1–3)	Display the Strength submenu. Validate that strength_choice is between 1 and 3. Map the choice to Upper Body, Lower Body, or Core & Flexibility.	Strength menu and selected category
duration (Integer: ≥ 0)	Prompt for workout duration. Validate that duration is greater than or equal to 0. Add the valid duration to total_strength.	Invalid duration warning or successful strength confirmation
main_choice = 3	Calculate total_active = total_cardio + total_strength. Determine whether the total is greater than or equal to 120 minutes. Display the formatted summary.	Total Cardio, Total Strength, Total Active, and Weekly Goal Status
main_choice = 4	End the main program loop.	Exit farewell message
3. Pseudocode
START

    Set total_cardio = 0
    Set total_strength = 0

    REPEAT

        Display "=========================================="
        Display "        PERSONAL FITNESS TRACKER"
        Display "=========================================="

        Display "--- MAIN MENU ---"
        Display "1. Log Cardio Workout"
        Display "2. Log Strength Workout"
        Display "3. View Activity Summary"
        Display "4. Exit"
        Display "Enter your choice (1-4):"

        Input main_choice

        WHILE main_choice < 1 OR main_choice > 4
            Display "Invalid. Choice must be 1, 2, 3, or 4. Try Again:"
            Input main_choice
        END WHILE

        IF main_choice = 1 THEN

            Display "--- CARDIO MENU ---"
            Display "1. Running / Jogging"
            Display "2. Cycling"
            Display "3. Swimming"
            Display "Enter cardio activity (1-3):"

            Input cardio_choice

            WHILE cardio_choice < 1 OR cardio_choice > 3
                Display "Invalid. Please enter 1, 2, or 3. Try Again!"
                Input cardio_choice
            END WHILE

            IF cardio_choice = 1 THEN
                Set activity = "Running / Jogging"
            ELSE IF cardio_choice = 2 THEN
                Set activity = "Cycling"
            ELSE
                Set activity = "Swimming"
            END IF

            Display "Enter duration in minutes:"
            Input duration

            WHILE duration < 0
                Display "Invalid. Please enter minutes >= 0:"
                Input duration
            END WHILE

            Set total_cardio = total_cardio + duration

            Display "Successfully added", duration, "minutes for", activity.

        ELSE IF main_choice = 2 THEN

            Display "--- STRENGTH MENU ---"
            Display "1. Upper Body"
            Display "2. Lower Body"
            Display "3. Core & Flexibility"
            Display "Enter strength category (1-3):"

            Input strength_choice

            WHILE strength_choice < 1 OR strength_choice > 3
                Display "Invalid. Please enter 1, 2, or 3. Try Again!"
                Input strength_choice
            END WHILE

            IF strength_choice = 1 THEN
                Set category = "Upper Body"
            ELSE IF strength_choice = 2 THEN
                Set category = "Lower Body"
            ELSE
                Set category = "Core & Flexibility"
            END IF

            Display "Enter duration in minutes:"
            Input duration

            WHILE duration < 0
                Display "Invalid. Please enter minutes >= 0:"
                Input duration
            END WHILE

            Set total_strength = total_strength + duration

            Display "Successfully added", duration, "minutes for", category.

        ELSE IF main_choice = 3 THEN

            Set total_active = total_cardio + total_strength

            Display "=========================================="
            Display "            ACTIVITY SUMMARY"
            Display "=========================================="

            Display "Total Cardio:    ", total_cardio, " minutes"
            Display "Total Strength:  ", total_strength, " minutes"
            Display "Total Active:    ", total_active, " minutes"

            IF total_active >= 120 THEN
                Display "Status: Goal achieved! You exceeded 120 weekly active minutes."
            ELSE
                Display "Status: Keep going! You have not reached 120 weekly active minutes yet."
            END IF

            Display "=========================================="

        ELSE IF main_choice = 4 THEN

            Display "Thank you for using Personal Fitness Tracker. Stay active!"

        END IF

    UNTIL main_choice = 4

END
