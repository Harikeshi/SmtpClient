string from= "sshchegolikhin@gmail.com";
            string to = "mant068@mail.ru,sshchegolikhin@yandex.ru";

            

            string subj = "privet";
            string body = "<h1>Hi!</h1>";

            var msg = new MailMessage(from, to, subj, body);

            System.Net.Mail.SmtpClient smtpclient = new System.Net.Mail.SmtpClient("smtp.gmail.com", 25);
            Console.WriteLine("{0}:{1}", smtpclient.Host, smtpclient.Port);            
            smtpclient.Credentials = new NetworkCredential("sshchegolikhin@gmail.com", "");


            Console.WriteLine(smtpclient.ClientCertificates);
            smtpclient.EnableSsl = true;
            Console.WriteLine("{0}:{1}:{2}:{3}",msg.From,msg.To,msg.Priority,msg.Sender);
            smtpclient.Send(msg);
            Console.WriteLine("Done.");