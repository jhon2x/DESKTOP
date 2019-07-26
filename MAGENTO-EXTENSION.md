//TOP 18 MAGENTO 2 CHALLENGES IN 2018
-- https://amasty.com/blog/top-18-magento-2-challenges-in-2018/#7_Magento_2_slow_performance
// How to add fee to order totals in Magento 2
https://magento.stackexchange.com/questions/92774/how-to-add-fee-to-order-totals-in-magento-2
steps:
app\
	code\
		AcmeWidgets\
			ProductPromoter\
				etc\
					sales.xml - (1)
					module.xml - (7)
				view\
					frontend\
						web\
							js\
								view\
									checkout\
										cart\
											totals\
												fee.js - (2) -- called by checkout_cart_index.xml
										summary\
											fee.js - (3)
							template\
								checkout\
									summary\
										fee.html - (4)
									cart\
										totals\
											fee.html - (5) - show in cart ex: fee: 1000 called by checkout_cart_index.xml
						layout\
							checkout_cart_index.xml - (8) -- for cart page
							checkout_index_index.xml - (9)
							sales_order_view.xml - (10) - show in account > order
				Model\
					Total\
						Fee.php - (6)						
				Block\
					Sales\
						Order\
							Fee.php	- (11)						
