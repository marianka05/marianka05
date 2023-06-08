from telegram.ext import Updater, CommandHandler


def start(update, context): 
    context.bot.send_message(chat_id=update.effective_chat.id, text="Привет! Это бот для жетонов.") 


def get_tokens(update, context): 
    # здесь код, который получает количество жетонов 
    # и записывает его в переменную tokens 
    tokens = 10 # пример 
    text = "У вас {} жетонов.".format(tokens) 
    context.bot.send_message(chat_id=update.effective_chat.id, text=text) 


def main(): 
    updater = Updater(token='5900710507:AAHowaTf-piSIm6Pkw4UCHR-VNhqMlchtyA', use_context=True) 
    dp = updater.dispatcher 
    dp.add_handler(CommandHandler('start', start)) 
    dp.add_handler(CommandHandler('get_tokens', get_tokens)) 
    updater.start_polling() 
    updater.idle() 


if name == 'main':
    main()
