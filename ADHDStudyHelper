# ADHD Study Helper Program
# This program helps students with ADHD by creating a personalized study plan,
# tracking their progress, awarding virtual coins for completed study sessions,
# and allowing them to redeem coins for rewards.

def get_user_input():
    """
    Prompt the user to enter subjects they need to study and available study time.
    Returns a list of subjects and the total study time.
    """
    # Ask the user for subjects separated by commas
    subjects_input = input("Enter subjects to study (separated by commas): ")
    # Split the input string into a list of subjects, removing extra spaces
    subjects_list = [subject.strip() for subject in subjects_input.split(',')]
    
    # Ask the user for the total available study time in hours
    time_available = int(input("Enter total available study time in hours: "))
    
    return subjects_list, time_available

def create_study_plan(subjects_list, time_available):
    """
    Generate a study plan based on the subjects and total available time.
    Distributes time equally among all subjects.
    Returns a dictionary with subjects as keys and allocated time as values.
    """
    # Calculate equal time allocation per subject
    time_per_subject = time_available / len(subjects_list)
    # Initialize an empty dictionary to store the study plan
    study_plan = {}
    
    # Assign equal time to each subject in the study plan
    for subject in subjects_list:
        study_plan[subject] = time_per_subject
    
    return study_plan

def simulate_study_session(subject, duration):
    """
    Simulate a study session for a given subject and duration.
    Waits for the user to confirm when they have completed the session.
    """
    print(f"Starting study session for {subject} for {duration} hour(s).")
    # Instruction for the user to press Enter upon completing the session
    input(f"Press Enter when you have completed the {subject} session...")

def award_coins(subject):
    """
    Award coins for completing a study session.
    Returns the number of coins earned for the session.
    """
    # Set a fixed number of coins earned per session (e.g., 10 coins)
    earned_coins = 10
    print(f"You've earned {earned_coins} coins for completing the {subject} session!")
    return earned_coins

def main():
    # Welcome message explaining the program purpose
    print("Welcome to the ADHD Study Helper Program!")
    
    # Get subjects and study time from the user
    subjects_list, time_available = get_user_input()
    
    # Validate that the user provided a positive study time
    while time_available <= 0:
        print("Please enter a valid amount of study time greater than 0.")
        # Ask for the study time again if the input was invalid
        time_available = int(input("Enter total available study time in hours: "))
    
    # Create a study plan based on user inputs
    study_plan = create_study_plan(subjects_list, time_available)
    
    # Initialize a variable to keep track of total coins earned
    total_coins = 0
    
    # Loop through each subject in the study plan and simulate a study session
    for subject, duration in study_plan.items():
        simulate_study_session(subject, duration)
        # Award coins after each completed session
        total_coins += award_coins(subject)
    
    # After all sessions are complete, display the total coins earned
    print("All study sessions completed.")
    print(f"Total coins earned: {total_coins}")
    
    # Display rewards catalog (simplified version)
    print("Here is the rewards catalog:")
    print("1. Sticker Pack - 20 coins")
    print("2. Extra Play Time - 50 coins")
    print("3. Small Toy - 100 coins")
    
    # Ask the user if they want to redeem coins for a reward
    redeem_response = input("Would you like to redeem some coins? (Yes/No): ")
    if redeem_response.lower() == "yes":
        # If yes, ask the user which reward they want to redeem
        selected_reward = input("Enter the reward you want to redeem: ")
        # In a full implementation, we would check if the user has enough coins and deduct them.
        # For simplicity, we just acknowledge the redemption here.
        print(f"You have redeemed {selected_reward}!")
    
    # End of the program message
    print("Thank you for using the ADHD Study Helper Program!")


# Ensure that main() runs when the script is executed
if __name__ == "__main__":
    main()
