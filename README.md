<client token="" op="{}">
    <events>
        <message var='msg'>

            <if condition="msg.content.startsWith('j!')">
                <if condition="!msg.author.bot">
                    <if condition="msg.content.slice(2) == 'avatar'">
                        <exe exec="msg.channel.send({embed:{title:msg.author.username,image:{url:msg.author.avatarURL}}})"></exe>
                    </if>
                    <if condition="msg.content.split(' ')[0].slice(2) == 'say'">
                        <var varname="sayvar" content="msg.content.split(' ').slice(1)" condition="true">
                            <exe exec="msg.reply(sayvar.join(' '))"></exe>
                        </var>
                    </if>
                    <if condition="msg.content.slice(2) == 'help'">
                        <reply content='Help'></reply>
                        <exe exec="msg.channel.send({embed:{title:'help',description:'avatar',color:65535}})"></exe>
                    </if>
                    <if condition="msg.content.slice(2) == 'spinner'">
                        <exevar varname='random' content='Math.floor(Math.random()*40)' exec="msg.channel.send('Spinner **%s** secods')"></exevar>
                    </if>
                </if>
            </if>
        </message>
        <ready>
            <log content="Start"></log>
        </ready>
    </events>
</client>
