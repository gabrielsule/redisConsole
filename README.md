# redisConsole

**Tabla de contenidos**

[TOC]

## Redis
--------

### Instalar Ubuntu en Win 10
- Desde el Store de Windows buscar Ubuntu 16.04 o 18.04 e instalar

### Preparar entorno en Ubuntu
```bash
sudo apt-get install make

sudo apt-get install gcc

sudo apt-get install tcl

sudo apt-get install build-essential

sudo apt-get update
```

### Instalar Redis
```bash
wget http://download.redis.io/redis-stable.tar.gz

tar xvzf redis-stable.tar.gz

cd redis-stable

make

make test
```

### Variables de entorno
`export PATH=$PATH:redis-stable/src`

### Inicializar servidor
`redis-server`

## C#
-----

### Instalar paquete de NuGet desde el manager
`ServiceStack.Redis.Core`


### Consola
```javascript
using System;
using ServiceStack.Redis;

namespace RedisApp
{
    class Program
    {
        static void Main(string[] args)
        {
            var manager = new RedisManagerPool("localhost:6379");
            using (var client = manager.GetClient())
            {
                client.Set("foo", "bar");
                Console.WriteLine("foo={0}", client.Get<string>("foo"));
            }

            Console.ReadLine();
        }
    }
}
```

`F5`