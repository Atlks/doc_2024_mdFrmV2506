=data trans
    ==rw mem
    load/store
    get/set
    print
    pop/push
    mov

    ==rw file
        rw
        

    ==rw net
        download  upload
        send rcv
        sendGet sendPost
        req response


=ctrlflow
    ==jmp goto
        run start exe  
        call/ret/invoke
        synchronized  lock  wait/notify

    ==choose foreach
        if else/choose
        switch case
        foreach/while
        break continue

    ==err process
        panic  recover defer
        try catch
         throw assert



=oop
    ==algo op
        (add sub mul div)
        mod

    ==lgc op
        ( and not or)

    ==crud
        select insert update delete
        query find save

    ==arr str op
        split/join
        append/substr

    ==other
         cast conver ToXx
        cmp (isXXX)
        encode /decode Parse


