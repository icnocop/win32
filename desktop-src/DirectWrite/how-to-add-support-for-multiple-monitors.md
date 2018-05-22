---
title: How to Add Support for Multiple Monitors
description: DirectWrite includes support for systems with multiple monitors.
ms.assetid: '62274126-49da-4166-8482-73aac2b29c26'
---

# How to Add Support for Multiple Monitors

[DirectWrite](direct-write-portal.md) includes support for systems with multiple monitors. Different monitors may have different pixel geometry (RGB, BGR, or FLAT) or other attributes. For more information about pixel geometry, see the [**DWRITE\_PIXEL\_GEOMETRY**](dwrite-pixel-geometry.md) reference topic. This topic will show you how to add support for multiple monitors to your DirectWrite application.

In order to support multiple monitors, you must handle the **WM\_WINDOWPOSCHANGED** window message. This message is sent when the window is moved, so you must check if the window has moved to a different monitor as shown in the following code.


```C++
case WM_WINDOWPOSCHANGED:
    {
        HMONITOR monitor = MonitorFromWindow(hwnd, MONITOR_DEFAULTTONULL);
        if (monitor != g_monitor)
        {
            g_monitor = monitor;
            if (g_spRenderTarget != NULL)
            {
                IDWriteRenderingParams* pRenderingParams = NULL;
                g_spDWriteFactory->CreateMonitorRenderingParams(monitor, &amp;pRenderingParams);

                g_spRenderTarget->SetTextRenderingParams(pRenderingParams);

                SafeRelease(&amp;pRenderingParams);
            }

            InvalidateRect(hwnd, NULL, TRUE);
        }
    }
    break;
```



If the window is located on a new monitor, then you must create rendering parameters for the new monitor by using the [**IDWriteFactory::CreateMonitorRenderingParams**](idwritefactory-createmonitorrenderingparams.md) method.

> [!Note]  
> Do not use the [**IDWriteFactory::CreateRenderingParams**](idwritefactory-createrenderingparams.md) method to create the rendering parameters, because it always creates parameters for the primary monitor.

 

When you have an [**IDWriteRenderingParams**](idwriterenderingparams.md) object, set the rendering parameters for the render target by using the [**ID2DRenderTarget::SetTextRenderingParams**](https://msdn.microsoft.com/library/windows/desktop/dd316898) method.

Finally, use the [**InvalidateRect**](https://msdn.microsoft.com/library/windows/desktop/dd145002) function to cause the window to redraw with the new rendering parameters.

 

 



