import datetime
from smtplib import SMTP

if __name__ == '__main__':
    toplantiAd = input("Toplantı,Etkinlik Adı Giriniz :")
    print(toplantiAd)
    toplantiGun =int(input("Toplantı,Etkinlik Günü Giriniz :"))
    print(toplantiGun)
    if (toplantiGun<0 or toplantiGun>31):
        print ("Hatalı Bir Gün Girdiniz, Saat 0,31 Arası Olmalıdır.")
        toplantiGun = int(input("Toplantı,Etkinlik Günü Giriniz :"))
        print(toplantiGun)
    toplantiAy =int(input("Toplantı,Etkinlik Ayını Giriniz :"))
    print(toplantiAy)
    if (toplantiAy<0 or toplantiAy>12):
        print ("Hatalı Bir Ay Girdiniz, Saat 0,12 Arası Olmalıdır.")
        toplantiAy = int(input("Toplantı,Etkinlik Ayını Giriniz :"))
        print(toplantiAy)
    toplantiYil =int(input("Toplantı,Etkinlik Yılını Giriniz :"))
    print(toplantiYil)
    if (toplantiYil < 2023):
        print("Hatalı Bir Yıl Girdiniz,Yıl 2023 veya daha büyük Olmalıdır.")
        toplantiYil = int(input("Toplantı,Etkinlik Yılını Giriniz :"))
        print(toplantiYil)
    toplantiSaat = int(input("Toplantı,Etkinlik Saatini Giriniz :"))
    print(toplantiSaat)
    if (toplantiSaat<0 or toplantiSaat>23):
        print ("Hatalı Bir Saat Girdiniz, Saat 0,23 Arası Olmalıdır.")
        toplantiSaat = int(input("Toplantı,Etkinlik Saatini Giriniz :"))
        print(toplantiSaat)
    toplantiDakika =int(input("Toplantı,Etkinlik Dakikasını Giriniz :"))
    print(toplantiDakika)
    if (toplantiDakika < 0 or toplantiDakika > 60):
        print("Hatalı Bir Dakika Girdiniz, Saat 0,60 Arası Olmalıdır.")
        toplantiDakika = int(input("Toplantı,Etkinlik Dakikasını Giriniz :"))
        print(toplantiDakika)
    tarih=datetime.datetime(toplantiYil,toplantiAy,toplantiGun,toplantiSaat,toplantiDakika)
    print (tarih)
    kisiSayi=int(input("Toplantı,Etkinliğe Kaç Kişi Katılacağını Giriniz :"))
    print (kisiSayi)
    if (kisiSayi<=0):
        print ("Hatalı Kişi Sayısı Girdiniz, 0dan Büyük Olmalıdır.")
        kisiSayi = int(input("Toplantı,Etkinliğe Kaç Kişi Katılacağını Giriniz :"))
        print(kisiSayi)
    x=("Toplantının Adı: " + toplantiAd + "\n" + "Toplantı Tarihi: " + str( tarih) + "\n" + "Toplantıya Katılacak Kişi Sayısı: " + str(kisiSayi))
try:
    subcjet = "Toplantı"
    message = x
    content = "Subject: {0}\n\n{1}".format(subcjet,message)

    myMailAdress = "xxxxxxx@gmail.com"
    password = "xxxxxxx"

    sendTo = "xxxxxxxx@gmail.com"

    mail = SMTP("smtp.gmail.com", 587)
    mail.ehlo()
    mail.starttls()
    mail.login(myMailAdress,password)
    mail.sendmail(myMailAdress, sendTo, content.encode("utf-8"))
    print("Mail Gönderme İşlemi Başarılı!")
except Exception as e:
    print("Hata Oluştu!\n {0}".format(e))
