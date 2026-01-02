@bot.message_handler(commands=['test'])
def bot_test(msg):
  draft_url = f"https://api.telegram.org/bot{bot.token}/sendMessageDraft"
  payload = {
    "chat_id": msg.chat.id,
    'message_thread_id': msg.message_thread_id,
    "draft_id": 12344,
    "text": 'test',
    'parse_mode': 'HTML'
  }
  resp = requests.post(draft_url, json=payload, timeout=5)
  print(resp.text)
