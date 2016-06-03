#Here are my code, and the one provided by professors can be found after mine. Intend to make comparison when I get to learn more
import simplegui
import random

#Global variables
player_choice = None
lst = ['box one', 'box two', 'box three']
prize = None
not_prize = None
play_times = 0
win_times = 0
win_per = 0

#Helper functions
            
def draw():
    global prize, not_prize, lst, player_choice
    local_lst = list(lst)
    prize = random.choice(local_lst)
    if prize == player_choice:
        local_lst.remove(prize)
    elif prize != player_choice:
        local_lst.remove(prize)
        local_lst.remove(player_choice)
    not_prize = random.choice(local_lst)
    
def initialize():
    global play_times, lst, player_choice
    print '\nPlease select a box! Only one contains the prize!'
    play_times = play_times + 1
    player_choice = None
    
def check_answer():
    global play_times, win_times, player_choice, win_per
    if player_choice == prize:
        win_times = win_times + 1
        print 'Congratulations!'
        print 'The prize was in', prize
        win_per = int(round(win_times * 100 / float(play_times)))
        print 'Your win percentage:', str(win_per) +  '%'
        
        
    elif player_choice != prize:
        print 'Too bad. :('
        print 'The prize was in', prize
        print 'Your win percentage:', str(win_per) +  '%'
    print 'play_times', play_times
    print 'win_times', win_times

#Event handlers

def box_one():
    global player_choice
    if player_choice in lst:
        pass
    else:
        player_choice = 'box one'
        print 'You chose box one.'
        draw()
        print 'By the way,', not_prize, 'is empty.'
        print 'Would you like to change your guess?'
    
def box_two():
    global player_choice
    if player_choice in lst:
        pass
    else:
        player_choice = 'box two'
        print 'You chose box two.'
        draw()
        print 'By the way,', not_prize, 'is empty.'
        print 'Would you like to change your guess?'
    
def box_three():
    global player_choice
    if player_choice in lst:
        pass
    else:
        player_choice = 'box three'
        print 'You chose box three.'
        draw()
        print 'By the way,', not_prize, 'is empty.'
        print 'Would you like to change your guess?'

def switch():
    global player_choice, prize, not_prize
    if player_choice == None:
        pass
    else:
        local_lst = list(lst)
        local_lst.remove(prize)
        local_lst.remove(not_prize)
        for i in lst:
            player_choice = i
        print 'You switched your box.'
        check_answer()
        initialize()

def not_switch():
    global player_choice
    if player_choice == None:
        pass
    else:
        print 'You did not switch your box.'
        check_answer()
        initialize()

#Frame
frame = simplegui.create_frame('Guess which box', 300, 300)
frame.set_canvas_background('Yellow')

#Register event handlers
frame.add_button('Box One', box_one, 100)
frame.add_button('Box Two', box_two, 100)
frame.add_button('Box Three', box_three, 100)
frame.add_button('Switch', switch, 100)
frame.add_button('Not Switch', not_switch, 100)

#Start everything
initialize()

frame.start()


#Here are the code provided by professors from Rice U
# Buttons
# Prize Boxes


# This is a sample program that allows a user to play a simple
#	carnival game. The user starts by picking one of three
#	boxes. The computer (or whoever is running the game) then
#	reveals the contents of one of the boxes the user did
#	not pick (which never reveals the prize). The user can 
#	then switch boxes if they would like, and the content 
#	of their box is then revealed.

import simplegui
import random

# Global Variables

canvas_color = "Black"
canvas_width = 300
canvas_height = 300

# Because counting starts from 0 in computer science, the
#	box selected by the player and the box that is revealed
#	will actually be player_choice + 1 and revealed + 1
player_choice = 0
revealed = 0
prize_box = 0
# This will prevent the player from hitting buttons when they
#	shouldn't
in_stage_one = True
# These will keep track of a win percentage
wins = 0
attempts = 0

# Helper Functions

def initialize():
    # Resets all of the values and re-determines the prize box
    global player_choice, revealed, prize_box, in_stage_one
    player_choice = 0
    revealed = 0
    prize_box = random.randrange(0,3)
    in_stage_one = True
    print "Please select a box! Only one contains the prize!"

def open_box():
    # Reveals a box that is not the one selected by the user
    #	and also does not contain a prize
    global revealed
    # Assigns num to be either -1 or +1
    # Num is a random direction starting from player_choice
    num = random.randrange(-1, 3, 2)
    revealed = (player_choice + num) % 3
    if revealed == prize_box:
        revealed = (revealed + num) % 3
    print "By the way, box", revealed + 1, "is empty."
    print "Would you like to change your guess?"

# Event Handlers

def choose_one():
    global player_choice, in_stage_one
    if in_stage_one:
        player_choice = 0
        in_stage_one = False
        print "You chose box one."
        open_box()
        

def choose_two():
    global player_choice, in_stage_one
    if in_stage_one:
        player_choice = 1
        in_stage_one = False
        print "You chose box two."
        open_box()
    
def choose_three():
    global player_choice, in_stage_one
    if in_stage_one:
        player_choice = 2
        in_stage_one = False
        print "You chose box three."
        open_box()
    
def switch():
    global player_choice, in_stage_one
    if not in_stage_one:
        # The modulus ensures that values above two go back to 0
        player_choice = (player_choice + 1) % 3
        # This makes sure that player_choice is not switched with revealed
        if player_choice == revealed:
            player_choice = (player_choice + 1) % 3
        print "You switched your box."
        get_result()
        
def no_switch():
    if not in_stage_one:
        print "You did not switch your box."
        get_result()
            
def get_result():
    global wins, attempts
    attempts += 1
    if player_choice == prize_box:
        print "Congratulations!"
        wins += 1
    else:
        print "Too bad. :("
    print "The prize was in box", prize_box + 1
    # Rounding the answer usually looks a bit nicer
    print "Your win percentage:", str(int(round(float(wins) / attempts * 100))) + "%"
    print
    initialize()

# Frame

frame = simplegui.create_frame("Let's make a deal!", canvas_width, canvas_height) 

# Register Event Handlers

frame.add_button("Box One", choose_one, 100)
frame.add_button("Box Two", choose_two, 100)
frame.add_button("Box Three", choose_three, 100)
frame.add_button("Switch", switch, 100)
frame.add_button("Don't Switch", no_switch, 100)

# Start Frame and Initialize Game

frame.start()
initialize()
