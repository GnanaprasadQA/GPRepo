# GPRepo
 Below code is to automate placing an order in the website http://automationpractice.com/index.php? and capture the screenshot of order placed 


		package OnlineShopping;

		import java.io.File;
		import java.util.concurrent.TimeUnit;
		import org.apache.commons.io.FileUtils;
		import org.openqa.selenium.By;
		import org.openqa.selenium.JavascriptExecutor;
		import org.openqa.selenium.OutputType;
		import org.openqa.selenium.TakesScreenshot;
		import org.openqa.selenium.WebDriver;
		import org.openqa.selenium.WebElement;
		import org.openqa.selenium.chrome.ChromeDriver;
		import org.openqa.selenium.interactions.Actions;
		import org.openqa.selenium.support.ui.Select;



		public class OnlineProductBuy {

		public static void main(String[] args) throws Exception{
		WebDriver driver = null;
		try{
			System.setProperty("webdriver.chrome.driver", "D:/drivers/chromedriver_win32/chromedriver.exe");
		
		driver=new ChromeDriver();
		driver.manage().window().maximize();
		driver.get("http://automationpractice.com/index.php");
		driver.manage().timeouts().implicitlyWait(15, TimeUnit.SECONDS);
		driver.findElement(By.xpath("//*[@id='header']/div[2]/div/div/nav/div[1]/a")).click();
		driver.findElement(By.xpath("//*[@id='email']")).sendKeys("gnanaprasad1993@gmail.com");
		driver.findElement(By.xpath("//*[@id='passwd']")).sendKeys("ABCabc@123");
		driver.findElement(By.xpath("//*[@id='SubmitLogin']/span/i")).click();
		driver.manage().timeouts().implicitlyWait(5, TimeUnit.SECONDS);
		driver.findElement(By.xpath("//*[@id='center_column']/div/div[1]/ul/li[3]/a/span")).click();
		driver.findElement(By.xpath("//*[@id='center_column']/div/a/span")).click();
		driver.manage().timeouts().implicitlyWait(3, TimeUnit.SECONDS);
		driver.findElement(By.xpath("//*[@id='firstname']")).clear();
		driver.findElement(By.xpath("//*[@id='firstname']")).sendKeys("Gnanaprasad");
		driver.findElement(By.xpath("//*[@id='lastname']")).clear();
		driver.findElement(By.xpath("//*[@id='lastname']")).sendKeys("R");
		driver.findElement(By.xpath("//*[@id='company']")).sendKeys("TCS");
		driver.findElement(By.xpath("//*[@id='address1']")).sendKeys("Chennai");
		driver.findElement(By.xpath("//*[@id='city']")).sendKeys("Olympia");
		Select sel=new Select(driver.findElement(By.xpath("//*[@id='id_state']")));
		sel.selectByVisibleText("Washington");
		driver.findElement(By.xpath("//*[@id='postcode']")).sendKeys("20001");
		Select sel2=new Select(driver.findElement(By.xpath("//*[@id='id_country']")));
		sel2.selectByValue("21");
		driver.findElement(By.xpath("//*[@id='phone']")).sendKeys("123456789");
		driver.findElement(By.xpath("//*[@id='phone_mobile']")).sendKeys("987654321");
		String address=driver.findElement(By.xpath("//*[@id='alias']")).getText();
		long Suffix=System.currentTimeMillis();
		address=address+Suffix;
		driver.findElement(By.xpath("//*[@id='alias']")).sendKeys(address);
		driver.findElement(By.xpath("//*[@id='submitAddress']/span")).click();
		
		
		Actions actions = new Actions(driver);
		WebElement target=driver.findElement(By.xpath("//*[@id='block_top_menu']/ul/li[1]/a"));
		actions.moveToElement(target).perform();
		
		driver.findElement(By.xpath("//*[@id='block_top_menu']/ul/li[1]/ul/li[2]/ul/li[3]/a")).click();
		driver.findElement(By.xpath("//*[@id='list']")).click();
		
		//for first item
		driver.findElement(By.xpath("//*[@id='center_column']/ul/li[1]/div/div/div[2]/h5/a")).click();
		WebElement button1 = driver.findElement(By.xpath("//*[@id='quantity_wanted_p']/a[2]/span"));
		for (int i = 0; i < 4; i++){
			 //click the button
			  button1.click();
		}
		Select sel3=new Select(driver.findElement(By.xpath("//*[@id='group_1']")));
		sel3.selectByVisibleText("L");
		driver.findElement(By.xpath("//*[@id='add_to_cart']/button/span")).click();
		driver.findElement(By.xpath("//*[@id='layer_cart']/div[1]/div[2]/div[4]/span/span")).click();
		
		//For second item
		Actions actions2 = new Actions(driver);
		WebElement target2=driver.findElement(By.xpath("//*[@id='block_top_menu']/ul/li[1]/a"));
		actions2.moveToElement(target2).perform();
		driver.findElement(By.xpath("//*[@id='block_top_menu']/ul/li[1]/ul/li[2]/ul/li[3]/a")).click();
		driver.findElement(By.xpath("//*[@id='list']")).click();
		driver.findElement(By.xpath("//*[@id='center_column']/ul/li[2]/div/div/div[2]/h5/a")).click();
		WebElement button2 = driver.findElement(By.xpath("//*[@id='quantity_wanted_p']/a[2]/span"));
		for (int i = 0; i < 4; i++){
			 //click the button
			  button2.click();
		}
		
		Select sel4=new Select(driver.findElement(By.xpath("//*[@id='group_1']")));
		sel4.selectByVisibleText("L");
		driver.findElement(By.xpath("//*[@id='add_to_cart']/button/span")).click();
		driver.findElement(By.xpath("//*[@id='layer_cart']/div[1]/div[2]/div[4]/span/span")).click();
		  
		//for third item
		Actions actions3 = new Actions(driver);
		WebElement target3=driver.findElement(By.xpath("//*[@id='block_top_menu']/ul/li[1]/a"));
		actions3.moveToElement(target3).perform();
		driver.findElement(By.xpath("//*[@id='block_top_menu']/ul/li[1]/ul/li[2]/ul/li[3]/a")).click();
		driver.findElement(By.xpath("//*[@id='list']")).click();
		driver.findElement(By.xpath("//*[@id='center_column']/ul/li[3]/div/div/div[2]/h5/a")).click();
		WebElement button3 = driver.findElement(By.xpath("//*[@id='quantity_wanted_p']/a[2]/span"));
		for (int i = 0; i < 4; i++){
			 //click the button
			  button3.click();
		}
		
		Select sel5=new Select(driver.findElement(By.xpath("//*[@id='group_1']")));
		sel5.selectByVisibleText("L");
		
		driver.findElement(By.xpath("//*[@id='add_to_cart']/button/span")).click();
		driver.findElement(By.xpath("//*[@id='layer_cart']/div[1]/div[2]/div[4]/a/span")).click();
		driver.findElement(By.xpath("//*[@id='center_column']/p[2]/a[1]/span")).click();
		driver.findElement(By.xpath("//*[@id='center_column']/form/p/button/span")).click();
		driver.findElement(By.xpath("//*[@id='cgv']")).click();
		driver.findElement(By.xpath("//*[@id='form']/p/button/span")).click();
		driver.findElement(By.xpath("//*[@id='HOOK_PAYMENT']/div[1]/div/p/a")).click();
		driver.findElement(By.xpath("//*[@id='cart_navigation']/button/span")).click();
		driver.findElement(By.xpath("//*[@id='center_column']/p/a")).click();
		
		 JavascriptExecutor js = (JavascriptExecutor) driver;
		 js.executeScript("window.scrollBy(0,500)");
		 
		 File screenshotFile = ((TakesScreenshot) driver).getScreenshotAs(OutputType.FILE);
		 File DestFile=new File("D://test.png");
		 FileUtils.copyFile(screenshotFile, DestFile);
		 
		 System.out.println("Ordered and screenshot taken successfully");
		 
		 driver.findElement(By.xpath("//*[@id='header']/div[2]/div/div/nav/div[2]/a")).click();
		 System.out.println("We logged out successfully");
		}
		
		catch(Exception e){
			e.printStackTrace();
		}
		 
		finally{
			driver.quit();
			}
		}}

