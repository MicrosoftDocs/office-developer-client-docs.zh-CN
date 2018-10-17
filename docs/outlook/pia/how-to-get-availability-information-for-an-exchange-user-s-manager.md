---
title: 获取 Exchange 用户的经理闲/忙状态信息
TOCTitle: Get availability information for an Exchange user's manager
ms:assetid: b59dd875-50c2-4f24-ba91-24429abf1b72
ms:mtpsurl: https://msdn.microsoft.com/library/Bb646996(v=office.15)
ms:contentKeyID: 55119849
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: 927389609e7a16a538cb480cc24891873ec1650c
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25405894"
---
# <a name="get-availability-information-for-an-exchange-users-manager"></a>获取 Exchange 用户的经理闲/忙状态信息

此示例在日历中显示用户的经理的下一个空闲 60 分钟时间段。

## <a name="example"></a>示例

该代码示例检查当前用户是不是 Exchange 用户。 如果是，并且当前用户有一个经理，则它通过调用 [AddressEntry](https://msdn.microsoft.com/library/bb611808\(v=office.15\)) 对象的 [GetExchangeUser](https://msdn.microsoft.com/library/bb609728\(v=office.15\)) 方法和 [ExchangeUser](https://msdn.microsoft.com/library/bb646656\(v=office.15\)) 对象的 [GetExchangeUserManager](https://msdn.microsoft.com/library/bb609574\(v=office.15\)) 方法来获取经理信息。 经理信息包含在 **ExchangeUser** 对象中，其中包括经理的闲/忙日程安排。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **Imports** 或 **using** 语句直接添加到此代码示例中的函数前面，这两个语句必须后跟公共类声明。 下面几段代码行展示了如何在 Visual Basic 和 C\# 中执行导入和分配操作。

```vb
Imports Outlook = Microsoft.Office.Interop.Outlook
```


```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```vb
Private Sub GetManagerOpenInterval()
    Const slotLength As Integer = 60
    Dim addrEntry As Outlook.AddressEntry = _
        Application.Session.CurrentUser.AddressEntry
    If addrEntry.Type = "EX" Then
        Dim manager As Outlook.ExchangeUser = _
            Application.Session.CurrentUser. _
            AddressEntry.GetExchangeUser(). _
            GetExchangeUserManager()
        If Not (manager Is Nothing) Then
            Dim freeBusy As String = _
            manager.GetFreeBusy(DateTime.Now, slotLength, True)
            For i As Integer = 1 To freeBusy.Length - 1
                If (freeBusy.Substring(i, 1) = "0") Then
                    ' Get number of minutes into
                    ' the day for free interval
                    Dim busySlot As Double = (i - 1) * slotLength
                    ' Get an actual date/time
                    Dim dateBusySlot As DateTime = _
                        DateTime.Now.Date.AddMinutes(busySlot)
                    If (dateBusySlot.TimeOfDay >= _
                        DateTime.Parse("8:00 AM").TimeOfDay And _
                        dateBusySlot.TimeOfDay <= _
                        DateTime.Parse("5:00 PM").TimeOfDay And _
                        Not (dateBusySlot.DayOfWeek = _
                        DayOfWeek.Saturday Or _
                        dateBusySlot.DayOfWeek = DayOfWeek.Sunday))Then
                        Dim sb As StringBuilder = New StringBuilder()
                        sb.AppendLine( _
                            manager.Name & " first open interval:")
                        sb.AppendLine(dateBusySlot.ToString("f"))
                        Debug.WriteLine(sb.ToString())
                    End If
                End If
            Next
        End If
    End If
End Sub
```


```csharp
private void GetManagerOpenInterval()
{
    const int slotLength = 60;
    Outlook.AddressEntry addrEntry =
        Application.Session.CurrentUser.AddressEntry;
    if (addrEntry.Type == "EX")
    {
        Outlook.ExchangeUser manager =
            Application.Session.CurrentUser.
            AddressEntry.GetExchangeUser().GetExchangeUserManager();
        if (manager != null)
        {
            string freeBusy = manager.GetFreeBusy(
                DateTime.Now, slotLength, true);
            for (int i = 1; i < freeBusy.Length; i++)
            {
                if (freeBusy.Substring(i, 1) == "0")
                {
                    // Get number of minutes into
                    // the day for free interval
                    double busySlot = (i - 1) * slotLength;
                    // Get an actual date/time
                    DateTime dateBusySlot =
                        DateTime.Now.Date.AddMinutes(busySlot);
                    if (dateBusySlot.TimeOfDay >=
                        DateTime.Parse("8:00 AM").TimeOfDay &
                        dateBusySlot.TimeOfDay <=
                        DateTime.Parse("5:00 PM").TimeOfDay &
                        !(dateBusySlot.DayOfWeek == 
                        DayOfWeek.Saturday |
                        dateBusySlot.DayOfWeek == DayOfWeek.Sunday))
                    {
                        StringBuilder sb = new StringBuilder();
                        sb.AppendLine(manager.Name
                            + " first open interval:");
                        sb.AppendLine(dateBusySlot.ToString("f"));
                        Debug.WriteLine(sb.ToString());
                    }
                }
            }
        }
    }
}
```

## <a name="see-also"></a>另请参阅

- [Exchange 用户](exchange-users.md)

