---
title: 查看对会议请求的所有响应
TOCTitle: Check all responses to a meeting request
ms:assetid: ebe10e5a-7f04-447a-bfc1-aa8a726cb0b3
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184650(v=office.15)
ms:contentKeyID: 55119881
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: a1dbc34cca35306ded436a30691c1cfb0f00fe6c
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25406160"
---
# <a name="check-all-responses-to-a-meeting-request"></a><span data-ttu-id="a98f2-102">查看对会议请求的所有响应</span><span class="sxs-lookup"><span data-stu-id="a98f2-102">Check all responses to a meeting request</span></span>

<span data-ttu-id="a98f2-103">此代码示例展示了如何检查每个收件人对会议请求的响应状态。</span><span class="sxs-lookup"><span data-stu-id="a98f2-103">This example shows how to check the status of each recipient’s response to a meeting request.</span></span>

## <a name="example"></a><span data-ttu-id="a98f2-104">示例</span><span class="sxs-lookup"><span data-stu-id="a98f2-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="a98f2-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="a98f2-105">The following code example is an excerpt from  [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)  , from Microsoft Press (ISBN 9780735622494, copyright Microsoft Press 2007, all rights reserved).</span></span>

<span data-ttu-id="a98f2-106">在下面的代码示例中，CheckAttendeeStatus 枚举表示会议请求的 [AppointmentItem](https://msdn.microsoft.com/library/bb645611\(v=office.15\)) 对象的 [Recipients](https://msdn.microsoft.com/library/bb646361\(v=office.15\)) 集合，并检查每个 [Recipient](https://msdn.microsoft.com/library/bb624370\(v=office.15\)) 对象的 [MeetingResponseStatus](https://msdn.microsoft.com/library/bb645283\(v=office.15\)) 属性。</span><span class="sxs-lookup"><span data-stu-id="a98f2-106">In the following code example,   enumerates the Recipients collection for the AppointmentItem object that represents a meeting request and examines the MeetingResponseStatus property of each Recipient object.</span></span> <span data-ttu-id="a98f2-107">每个 **Recipient** 对象都表示会议请求的收件人。</span><span class="sxs-lookup"><span data-stu-id="a98f2-107">Each **Recipient** object represents a recipient of the meeting request.</span></span> <span data-ttu-id="a98f2-108">**MeetingResponseStatus** 属性的值可以是以下 [OlResponseStatus](https://msdn.microsoft.com/library/bb644655\(v=office.15\)) 枚举值之一：</span><span class="sxs-lookup"><span data-stu-id="a98f2-108">The value of the **MeetingResponseStatus** property can be one of the following [OlResponseStatus](https://msdn.microsoft.com/library/bb644655\(v=office.15\)) enumeration values:</span></span>

- <span data-ttu-id="a98f2-109">[olResponseAccepted](https://msdn.microsoft.com/library/bb644655\(v=office.15\))</span><span class="sxs-lookup"><span data-stu-id="a98f2-109">[olResponseAccepted](https://msdn.microsoft.com/library/bb644655\(v=office.15\))</span></span>
- <span data-ttu-id="a98f2-110">[olResponseDeclined](https://msdn.microsoft.com/library/bb644655\(v=office.15\))</span><span class="sxs-lookup"><span data-stu-id="a98f2-110">[olResponseDeclined](https://msdn.microsoft.com/library/bb644655\(v=office.15\))</span></span>
- <span data-ttu-id="a98f2-111">[olResponseNone](https://msdn.microsoft.com/library/bb644655\(v=office.15\))</span><span class="sxs-lookup"><span data-stu-id="a98f2-111">[olResponseNone](https://msdn.microsoft.com/library/bb644655\(v=office.15\))</span></span>
- <span data-ttu-id="a98f2-112">[olResponseNotResponded](https://msdn.microsoft.com/library/bb644655\(v=office.15\))</span><span class="sxs-lookup"><span data-stu-id="a98f2-112">[olResponseNotResponded](https://msdn.microsoft.com/library/bb644655\(v=office.15\))</span></span>
- <span data-ttu-id="a98f2-113">[olResponseOrganized](https://msdn.microsoft.com/library/bb644655\(v=office.15\))</span><span class="sxs-lookup"><span data-stu-id="a98f2-113">[olResponseOrganized](https://msdn.microsoft.com/library/bb644655\(v=office.15\))</span></span>
- <span data-ttu-id="a98f2-114">[olResponseTentative](https://msdn.microsoft.com/library/bb644655\(v=office.15\))</span><span class="sxs-lookup"><span data-stu-id="a98f2-114">[olResponseTentative](https://msdn.microsoft.com/library/bb644655\(v=office.15\))</span></span>

<span data-ttu-id="a98f2-115">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="a98f2-115">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the   variable when you import the Microsoft.Office.Interop.Outlook namespace.</span></span> <span data-ttu-id="a98f2-116">不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="a98f2-116">The using statement must not occur directly before the functions in the code example but must be added before the public   declaration.</span></span> <span data-ttu-id="a98f2-117">下面的代码行展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="a98f2-117">The following line of code shows how to do the import and assignment in C#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void CheckAttendeeStatus()
{
    Outlook.AppointmentItem appt = Application.Session.
        GetDefaultFolder(Outlook.OlDefaultFolders.olFolderCalendar).
        Items.Find("[Subject]='Sales Strategy FY2007'")
        as Outlook.AppointmentItem;
    if (appt != null)
    {
        foreach (Outlook.Recipient recip in appt.Recipients)
        {
            switch (recip.MeetingResponseStatus)
            {
                case Outlook.OlResponseStatus.olResponseAccepted:
                    Debug.WriteLine("Accepted: " + recip.Name);
                    break;
                case Outlook.OlResponseStatus.olResponseTentative:
                    Debug.WriteLine("Tentative: " + recip.Name);
                    break;
                case Outlook.OlResponseStatus.olResponseDeclined:
                    Debug.WriteLine("Declined: " + recip.Name);
                    break;
                case Outlook.OlResponseStatus.olResponseOrganized:
                    Debug.WriteLine("Organizer: " + recip.Name);
                    break;
                case Outlook.OlResponseStatus.olResponseNone:
                    Debug.WriteLine("None: " + recip.Name);
                    break;
                case Outlook.OlResponseStatus.olResponseNotResponded:
                    Debug.WriteLine("Not responded: " + recip.Name);
                    break;
            }
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="a98f2-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a98f2-118">See also</span></span>

- [<span data-ttu-id="a98f2-119">会议请求</span><span class="sxs-lookup"><span data-stu-id="a98f2-119">Meeting Requests</span></span>](meeting-requests.md)
