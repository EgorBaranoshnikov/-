import telebot
import config

bot = telebot.TeleBot(config.TOKEN)

@bot.message_handler(content_types=["text"])
def welcom(message):
    bot.send_message(message.chat.id, "добро пожаловоть, {0.first_name}!\nЭтот бот дужен для формирования привычек".format(message.from_user, bot.get_me(),parse_mode="html"))

def b(message):
    bot.send_message(message.chat.id, message.text)

bot.polling(none_stop=True)
