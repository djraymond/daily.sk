# daily key in minecraft 24 uur slot


command /daily:
    trigger:
        if {time.%player%} is not set:
            set {time.%player%} to 0
            add {server.time} to {time.%player%}
        if {time.%player%} - {server.time} is less than or equal to 0:
            make player execute command "crates key %player% daily"
            clear {time.%player%}
            add {server.time} to {time.%player%}
            add 24 to {time.%player%}
        else:
            send "You need to wait %{time.%player%} - {server.time}% Hours to use this command again" to player
 
every 1 hour:
    add 1 to {server.time}
