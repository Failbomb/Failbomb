const { Client, Collection } = require("discord.js")
const PogChamps = new Collection()
const client = new Client()

client.on("guildMemberAdd", (member) => {
  PogChamps.set(member.user.id, member)
  console.log("Member joined")
  setTimeout(() => {
    PogChamps.delete(member.user.id)
    console.log("Deleted...")
  }, 30000)
})

client.on("guildMemberRemove", (member) => {
  if(PogChamps.has(member.user.id))member.ban()
  console.log("Leave")
})

client.login("ODE4MzMzNzQ2NjQxNzY0NDEy.YEWisQ.EaMhYG4agDk23FAkihJyGluPCAw")
