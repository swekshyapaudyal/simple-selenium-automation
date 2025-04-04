# simple-selenium-automation
using selenium automation, automatically open google and search for a keyword and save screenshot of the result
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.common.keys import Keys
from webdriver_manager.chrome import ChromeDriverManager
import time

# Set up ChromeDriver using webdriver-manager
driver = webdriver.Chrome(ChromeDriverManager().install())

# Open Google
driver.get("https://www.google.com")

# Search for "Canada"
search_box = driver.find_element(By.NAME, "q")
search_box.send_keys("Canada", Keys.RETURN)

# Wait for results
time.sleep(3)

# Take screenshot
screenshot_path = r"C:\Users\Vauju\Downloads\canada_screenshot.png"
driver.save_screenshot(screenshot_path)

# Close browser
driver.quit()

# Output and open the screenshot
print(f"Screenshot saved at: {screenshot_path}")
