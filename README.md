# Switch_Tabs
Switch tabs in UITabBarController programmatically using swift

Consider in your tabbed application you faced the situation when you performed a task in one tab and after completion/ failure you want to redirect to another tab.

1: Add UIApplication Extension

<pre>
extension UIApplication {
/*function will return reference to tabbarcontroller */

func tabbarController() -> UIViewController? {
  guard let vcs = self.keyWindow?.rootViewController?.childViewControllers else { return nil }
  
  for vc in vcs {
    if  let _ = vc as? TabBarViewController {
    return vc
    }
   }
   return nil
  }
}
<pre>

2: How to use

<pre>
guard let tabbarController = UIApplication.shared.tabbarController() as? RootTabBarViewController else { return }

tabbarController.selectedIndex = 0  // Will redirect to first tab ( index = 0 )
<pre>
