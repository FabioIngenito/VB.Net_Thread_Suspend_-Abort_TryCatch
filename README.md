# VB.Net_Thread_Suspend_-Abort_TryCatch
Utilizando Thread - Suspend - Abort - Try Catch

Using Thread - Suspend - Abort - Try Catch



Pessoal, segue uma aplica��o que usa thread.

Folks, follows an application that uses thread.


Algumas coisas importantes:

Some important things:

- Objetos criados fora de threads n�o podem ser alterados dentro delas.

- Objects created out of threads cannot be changed inside them.

- Procure n�o endere�ar metodos de objetos diretamente, sen�o voce n�o conseguir� pegar as exception.

- Try not to address object methods directly, otherwise you will not be able to get the exception.



'=============================================

'Nesse exemplo nunca cai no Catch

'In this example, it never falls into Catch

'=============================================

Try

�� dim objThread as new Thread(AdressOf objClasse.Processar)

�� objThread.Start()

Catch ex as Exception

�� 'Nunca cai no catch

�� Msgbox(ex.message)

End Try


'=============================================

'Maneira mais aconselhavel, desse jeito voce pega as exception

'Most advisable way, this way you get the exception

'=============================================

Try

�� dim objThread as new Thread(AdressOf ChamaThread)

Catch ex as Exception

�� Msgbox(ex.message)

End Try

'---------------------------------------------

Private Sub ChamaThread

Try

�� objClasse.Processar

Catch ex as Exception

����'Trate todos os seus erros aqui, n�o de throw

����Msgbox(ex.message)

End Try

End Sub 

'=============================================


http://vbmania.com.br/index.php?modulo=detalhe&id=9245
