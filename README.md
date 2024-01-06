using System;
using System.Collections.Generic;
using System.Linq;
using System.Threading.Tasks;
using System;
using System;

namespace celulares
{
    public abstract class Smartphone
    {
        public string Marca { get; set; }
        public string Modelo { get; set; }

        public Smartphone(string marca, string modelo)
        {
            Marca = marca;
            Modelo = modelo;
        }

        public abstract void Ligar();
        public abstract void Desligar();
        public abstract void EnviarMensagem(string mensagem);

        // TODO: Implementar o método abstrato InstalarAplicativo
        public abstract void InstalarAplicativo(string aplicativo);
    }

    public class Nokia : Smartphone
    {
        public Nokia(string modelo) : base("Nokia", modelo)
        {
        }

        public override void Ligar()
        {
            Console.WriteLine($"{Marca} {Modelo} ligado.");
        }

        public override void Desligar()
        {
            Console.WriteLine($"{Marca} {Modelo} desligado.");
        }

        public override void EnviarMensagem(string mensagem)
        {
            Console.WriteLine($"Enviando mensagem do {Marca} {Modelo}: {mensagem}");
        }

        // TODO: Sobrescrever o método InstalarAplicativo para Nokia
        public override void InstalarAplicativo(string aplicativo)
        {
            Console.WriteLine($"Instalando aplicativo {aplicativo} no {Marca} {Modelo}");
        }
    }

    public class Iphone : Smartphone
    {
        public Iphone(string modelo) : base("iPhone", modelo)
        {
        }

        public override void Ligar()
        {
            Console.WriteLine($"{Marca} {Modelo} ligado.");
        }

        public override void Desligar()
        {
            Console.WriteLine($"{Marca} {Modelo} desligado.");
        }

        public override void EnviarMensagem(string mensagem)
        {
            Console.WriteLine($"Enviando mensagem do {Marca} {Modelo}: {mensagem}");
        }

        // TODO: Sobrescrever o método InstalarAplicativo para iPhone
        public override void InstalarAplicativo(string aplicativo)
        {
            Console.WriteLine($"Instalando aplicativo {aplicativo} no {Marca} {Modelo}");
        }
    }

    class Program
    {
        static void Main()
        {
            Nokia nokiaPhone = new Nokia("Lumia 950");
            Iphone iphone = new Iphone("11 Pro");

            nokiaPhone.Ligar();
            nokiaPhone.EnviarMensagem("Olá, como vai?");
            nokiaPhone.InstalarAplicativo("WhatsApp");
            nokiaPhone.Desligar();

            Console.WriteLine();

            iphone.Ligar();
            iphone.EnviarMensagem("Hello, how are you?");
            iphone.InstalarAplicativo("Instagram");
            iphone.Desligar();
        }
    }
}
