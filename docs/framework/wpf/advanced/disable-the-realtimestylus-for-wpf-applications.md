---
title: Wyłącz RealTimeStylus dla aplikacji WPF
ms.date: 03/30/2017
ms.assetid: e0525309-5ede-4782-837d-dbf6e5554859
ms.openlocfilehash: ddf4a7f4488f957b2f413d61ad02aa59beba30f6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545665"
---
# <a name="disable-the-realtimestylus-for-wpf-applications"></a>Wyłącz RealTimeStylus dla aplikacji WPF
Windows Presentation Foundation (WPF) zawiera wbudowaną obsługą przetwarzania wprowadzania dotykowego systemu Windows 7. Obsługę jest dostarczany za pośrednictwem wprowadzania danych w czasie rzeczywistym piórem platformy tablet jako <xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, i <xref:System.Windows.UIElement.OnStylusMove%2A> zdarzenia. Windows 7 także wielodotyku danych wejściowych jako komunikaty okna Win32 WM_TOUCH. Te dwa interfejsy API wzajemnie się wykluczają na tym samym HWND. Wprowadzania dotykowego włączenie za pośrednictwem platformy tablet (wartość domyślna dla aplikacji WPF) wyłącza WM_TOUCH wiadomości. W związku z tym na potrzeby odbierania komunikatów touch z okna WPF WM_TOUCH, należy wyłączyć obsługę wbudowanych Pióro na platformie WPF. Ma to zastosowanie w przypadku takich jak obsługującym składnik, który używa WM_TOUCH okna WPF.  
  
 Aby wyłączyć nasłuchiwanie wprowadzania danych piórem WPF, usuń wszelkie wsparcie tablet dodane przez okno WPF.  
  
## <a name="example"></a>Przykład  
 Następujący przykładowy kod przedstawia sposób usuwania domyślnego typu tablet platformy obsługiwane przy użyciu odbicia.  
  
```  
public static void DisableWPFTabletSupport()  
{  
    // Get a collection of the tablet devices for this window.    
    TabletDeviceCollection devices = System.Windows.Input.Tablet.TabletDevices;  
  
    if (devices.Count > 0)  
    {     
        // Get the Type of InputManager.  
        Type inputManagerType = typeof(System.Windows.Input.InputManager);  
  
        // Call the StylusLogic method on the InputManager.Current instance.  
        object stylusLogic = inputManagerType.InvokeMember("StylusLogic",  
                    BindingFlags.GetProperty | BindingFlags.Instance | BindingFlags.NonPublic,  
                    null, InputManager.Current, null);  
  
        if (stylusLogic != null)  
        {  
            //  Get the type of the stylusLogic returned from the call to StylusLogic.  
            Type stylusLogicType = stylusLogic.GetType();  
  
            // Loop until there are no more devices to remove.  
            while (devices.Count > 0)  
            {  
                // Remove the first tablet device in the devices collection.  
                stylusLogicType.InvokeMember("OnTabletRemoved",  
                        BindingFlags.InvokeMethod | BindingFlags.Instance | BindingFlags.NonPublic,  
                        null, stylusLogic, new object[] { (uint)0 });  
            }                  
        }  
  
    }  
}  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Przechwytywanie danych wejściowych z pisaka](../../../../docs/framework/wpf/advanced/intercepting-input-from-the-stylus.md)
