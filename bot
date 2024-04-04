from selenium import webdriver
from time import sleep
from selenium.webdriver.common.by import By
from selenium.webdriver import Keys
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC
import random

driver = webdriver.Chrome()

username = "instagram login"
password = "instagram password"

driver.get("https://www.instagram.com/")
sleep(2)

cookie = driver.find_element(By.XPATH, f'//button[text()="Разрешить все cookie"]')
cookie.click()

text_field = driver.find_element(by=By.NAME, value="username")
text_field.clear()
text_field.send_keys(username)
sleep(2)

text_field2 = driver.find_element(by=By.NAME, value="password")
text_field2.clear()
text_field2.send_keys(password + Keys.ENTER)
sleep(5)

driver.execute_script("document.getElementsByClassName('x1i10hfl xjqpnuy xa49m3k xqeqjp1 x2hbi6w xdl72j9 x2lah0s xe8uvvx xdj266r x11i5rnm xat24cr x1mh8g0r x2lwn1j xeuugli x1hl2dhg xggy1nq x1ja2u2z x1t137rt x1q0g3np x1lku1pv x1a2a7pz x6s0dn4 xjyslct x1ejq31n xd10rxx x1sy0etr x17r0tee x9f619 x1ypdohk x1f6kntn xwhw2v2 xl56j7k x17ydfre x2b8uid xlyipyv x87ps6o x14atkfc xcdnw81 x1i0vuye xjbqb8w xm3z3ea x1x8b98j x131883w x16mih1h x972fbf xcfux6l x1qhh985 xm0m39n xt0psk2 xt7dq6l xexx8yu x4uap5 x18d9i69 xkhd6sd x1n2onr6 x1n5bzlp x173jzuc x1yc6y37')[0].click()")
sleep(5)
driver.execute_script("document.getElementsByClassName('_a9-- _ap36 _a9_1')[0].click()")

hashtag = "germany"
driver.get(f"https://www.instagram.com/explore/tags/{hashtag}")
sleep(10)
links = driver.find_elements(by=By.TAG_NAME, value="a")

post_urls = []
for item in links:
    link = item.get_attribute("href")

    if "/p/" in link:
        post_urls.append(link)
        print(link)


for url in post_urls:
    driver.get(url)
    like_button = WebDriverWait(driver, 10).until(EC.element_to_be_clickable((By.XPATH, '//div[@class="x1i10hfl x972fbf xcfux6l x1qhh985 xm0m39n x9f619 xe8uvvx xdj266r x11i5rnm xat24cr x1mh8g0r x16tdsg8 x1hl2dhg xggy1nq x1a2a7pz x6s0dn4 xjbqb8w x1ejq31n xd10rxx x1sy0etr x17r0tee x1ypdohk x78zum5 xl56j7k x1y1aw1k x1sxyh0 xwib8y2 xurb0ha xcdnw81"]')))
    like_button.click()
    sleep(random.randrange(20, 30))
