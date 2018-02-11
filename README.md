# Exercice-2

Esta seria mi solución: 

Me he creado una clase base `BaseMessage` con dos métodos virtual `WriteMessageBase` y `WriteSomeAdditionalMessage`, las clases `MessageA`, `MessageB`, `MessageC` heredan de la clase base `BaseMessage` e implementan o no los métodos de la clase base.

``` c#
		public class BaseMessage
        {
            public virtual void WriteMessageBase() { }

            public virtual void WriteSomeAdditionalMessage() { }
        }

        public class MessageA : BaseMessage
        {
            public override void WriteMessageBase()
            {
                Console.WriteLine("Mensaje base de A");
            }
        }

        public class MessageB : BaseMessage
        {
            public override void WriteMessageBase()
            {
                Console.WriteLine("Mensaje base de B");
            }

            public override void WriteSomeAdditionalMessage()
            {
                Console.WriteLine("Mensaje adicional de B");
            }
        }

        public class MessageC : BaseMessage
        {
            public override void WriteMessageBase()
            {
                Console.WriteLine("Mensaje base de C");
            }
        }

        public static void MethodForExercice2(BaseMessage message)
        {
            message.WriteMessageBase();
            message.WriteSomeAdditionalMessage();
        }
```
Ejemplo de funcionamiento:
``` c#
        static void Main(string[] args)
        {
            var messageA = new MessageA();
            var messageB = new MessageB();
            var messageC = new MessageC();

            MethodForExercice2(messageA);
            MethodForExercice2(messageB);
            MethodForExercice2(messageC);

            Console.ReadLine();
        }
 ```

Resultado:

    Mensaje base de A
    Mensaje base de B
    Mensaje adicional de B
    Mensaje base de C
