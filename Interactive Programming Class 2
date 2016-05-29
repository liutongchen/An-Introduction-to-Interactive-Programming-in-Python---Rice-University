import simplegui

#Global variables

question_1 = "'R' comes before 'Q' in the alphabet."
answer_1 = False
question_2 = "Africa is a continent."
answer_2 = True
question_3 = "Indentation is not important in CodeSkulptor."
answer_3 = False
question_4 = "5 + 2 * 3 = 21"
answer_4 = False
question_5 = "Computer Science is AWESOME!!!"
answer_5 = True

player_answer = ''
cur_question = question_1
cur_answer = answer_1
question_number = 0

answer_dict = {}
question_lst = [question_1, question_2, question_3, question_4, question_5]
answer_lst = [answer_1, answer_2, answer_3, answer_4, answer_5]


#Helper functions

def next_question():
    global question_number, cur_question, cur_answer
    if (cur_question in question_lst) and (cur_question != question_5):
        question_number = question_lst.index(cur_question) + 1
        cur_question = question_lst[question_number]
        cur_answer = answer_lst[question_number]
        print_question()

    elif cur_question == question_5:
        print 'This is the end'
    
        
def check_answer():
    global cur_question, question_number, cur_answer
    if player_answer == cur_answer:
        print 'Correct!'

    elif player_answer != cur_answer:
        print 'Incorrect!'
    next_question()
    
    
def print_question():
    print 'Question', question_number + 1
    print cur_question

    
    
#define event handlers

def true_button():
    global player_answer
    player_answer = True
    check_answer()

def false_button():
    global player_answer
    player_answer = False
    check_answer()

def restart_button():
    global cur_question, cur_answer,question_number
    cur_question = question_1
    cur_answer = answer_1
    question_number = 0
    print_question()
    

#create a frame
frame = simplegui.create_frame('Q&A Test', 200, 200)
frame.set_canvas_background('fuchsia')

#register event handlers
frame.add_button('True', true_button, 60)
frame.add_button('False', false_button, 60)
frame.add_button('Restart', restart_button, 60)

#start frame&timers
restart_button()
frame.start()
