# The key idea of this program is to equate the strings
# "rock", "paper", "scissors", "lizard", "Spock" to numbers
# as follows:
#
# 0 - rock
# 1 - Spock
# 2 - paper
# 3 - lizard
# 4 - scissors

rpsls_rules = {'rock': 0, 'Spock': 1, 'paper': 2, 'lizard': 3, 'scissors': 4}
while True:
    player_choice = raw_input('Please enter your choice: ')
    if player_choice in rpsls_rules:
        player_num = rpsls_rules[player_choice]
        import random
        comp_num = random.randrange(0, 5)
        for key, value in rpsls_rules.items():
            if comp_num == value:
                comp_choice = key
        print 'You choose', player_choice, 'and computer choose', comp_choice
        modular_five = (player_num - comp_num) % 5
        if modular_five == 0:
            print 'It\'s a tie.'
        elif (modular_five == 1) or (modular_five == 2):
            print 'You win! :)'
        elif (modular_five == 3) or (modular_five == 4):
            print 'You lose :('
        else:
            print 'Something\'s wrong.'
        print
    elif (player_choice == 'Done') or (player_choice == 'done'):
        print 'End of the game but not the love for Sheldon'
    else:
        print 'Oops, something\'s wrong and I don\'t know what it is.'
