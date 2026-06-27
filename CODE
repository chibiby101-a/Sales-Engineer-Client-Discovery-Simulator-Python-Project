from random import randint

EASY_LEVEL_TURNS = 10
HARD_LEVEL_TURNS = 5


def recommend_solution(budget):
    if budget <= 10000:
        return "Fortinet Firewall - Best for small businesses"
    elif budget <= 50000:
        return "Cisco Meraki - Best for medium businesses with cloud management"
    else:
        return "Palo Alto Networks - Best for enterprise-grade security"


def check_answer(user_guess, actual_budget, turns):
    """Checks the user's budget estimate and returns turns remaining."""
    if user_guess > actual_budget:
        print("Your estimate is too high. The client may have budget limitations.")
        return turns - 1
    elif user_guess < actual_budget:
        print("Your estimate is too low. The client may need a stronger solution.")
        return turns - 1
    else:
        print(f"\nCorrect! The client's budget is ${actual_budget}.")
        print(f"Recommended Solution: {recommend_solution(actual_budget)}")
        return turns


def set_difficulty():
    level = input("Choose client type. Type 'small' or 'enterprise': ").lower()

    if level == "small":
        return EASY_LEVEL_TURNS
    else:
        return HARD_LEVEL_TURNS


def game():
    print("💼 Sales Engineer Client Discovery Simulator")
    print("Your goal is to estimate the client's IT budget.")
    print("Then recommend the right cybersecurity solution.")

    company_name = input("\nClient company name: ")
    pain_point = input("Client pain point: ")
    company_size = input("Company size (Small/Medium/Large): ")

    actual_budget = randint(1, 100) * 1000
    turns = set_difficulty()
    guess = 0

    print(f"\nClient Profile:")
    print(f"Company: {company_name}")
    print(f"Pain Point: {pain_point}")
    print(f"Company Size: {company_size}")

    while guess != actual_budget:
        print(f"\nYou have {turns} discovery questions remaining.")

        guess = int(input("Estimate the client's budget: $"))

        turns = check_answer(guess, actual_budget, turns)

        if guess == actual_budget:
            print("\nSales Engineer Summary:")
            print(f"{company_name} is a {company_size} company.")
            print(f"Their main issue is: {pain_point}")
            print(f"Proposed solution: {recommend_solution(actual_budget)}")
            print("Next step: Schedule a technical demo with the client.")
            break

        if turns == 0:
            print("\nYou ran out of discovery attempts.")
            print(f"The actual client budget was ${actual_budget}.")
            print(f"Suggested Solution: {recommend_solution(actual_budget)}")
            print("Tip: Ask better questions about company size, pain points, and budget.")
            return

        print("Continue discovery and refine your estimate.")


game()
