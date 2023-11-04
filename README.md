import os
import random

intents = discord.Intents.default()
intents.message_content = True

bot = commands.Bot(command_prefix='$', intents=intents)

@bot.event
async def on_ready():
    print(f'We have logged in as {bot.user}')

@bot.command()
async def hello(ctx):
    await ctx.send(f'Hello! I am {bot.user}!')

@bot.command()
async def bye(ctx):
    await ctx.send(f'Bye little giga chad!')

@bot.command()
async def dmem(ctx):
    img1_name = random.choice(os.listdir('images1'))
    with open(f'images1/{img1_name}', 'rb') as f:
            picture = discord.File(f)
   # Можем передавать файл как параметр!
    await ctx.send(file=picture)

@bot.command()
async def mem(ctx):
    img_name = random.choice(os.listdir('images'))
    with open(f'images/{img_name}', 'rb') as f:
            picture = discord.File(f)
   # Можем передавать файл как параметр!
    await ctx.send(file=picture)



bot.run("MTE2MjcxNzgyNTYxMDMwMTU1MA.GVkHeL.2Xi32CcUQcVoKA9J12f5DFj8IqPZNR5whKxWXA")

