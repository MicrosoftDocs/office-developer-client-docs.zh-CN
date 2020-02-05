---
title: 获取并登录 Outlook 实例
TOCTitle: Get and sign in to an instance of Outlook
ms:assetid: 7f5057dc-4232-4dc7-b597-16ff5f7bcd7d
ms:mtpsurl: https://docs.microsoft.com/office/client-developer/outlook/pia/how-to-get-and-log-on-to-an-instance-of-outlook?redirectedfrom=MSDN
ms:contentKeyID: 55119926
ms.date: 12/03/2019
mtps_version: v=office.15
localization_priority: Priority
ms.openlocfilehash: 5bae79531e7d2be39610194e0b59477fcee28c15
ms.sourcegitcommit: 31b0a7373ff74fe1d6383c30bc67d7675b73d283
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2020
ms.locfileid: "41773699"
---
# <a name="get-and-sign-in-to-an-instance-of-outlook"></a><span data-ttu-id="24668-102">获取并登录 Outlook 实例</span><span class="sxs-lookup"><span data-stu-id="24668-102">Get and sign in to an instance of Outlook</span></span>

<span data-ttu-id="24668-103">本主题介绍了如何获取表示本地计算机上正在运行的 Microsoft Outlook 有效实例的 [Application](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook.application?redirectedfrom=MSDN&view=outlook-pia) 对象，或新建 Outlook 示例，然后登录默认配置文件并返回相应 Outlook 实例。</span><span class="sxs-lookup"><span data-stu-id="24668-103">This topic shows how to obtain an [Application](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook.application?redirectedfrom=MSDN&view=outlook-pia) object that represents an active instance of Microsoft Outlook, if there is one running on the local computer, or to create a new instance of Outlook, sign in to the default profile, and return that instance of Outlook.</span></span>

## <a name="example"></a><span data-ttu-id="24668-104">示例</span><span class="sxs-lookup"><span data-stu-id="24668-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="24668-105">Helmut Obertanner 提供了下面的代码示例。</span><span class="sxs-lookup"><span data-stu-id="24668-105">Helmut Obertanner provided the following code examples.</span></span> <span data-ttu-id="24668-106">Helmut 拥有 Visual Studio Office 开发人员工具和 Outlook 方面的专业知识。</span><span class="sxs-lookup"><span data-stu-id="24668-106">Helmut's expertise is in Office Developer Tools for Visual Studio and Outlook.</span></span> 

<span data-ttu-id="24668-107">下面的代码示例包含 Sample 类的 GetApplicationObject 方法（作为 Outlook 加载项项目的一部分实现）。</span><span class="sxs-lookup"><span data-stu-id="24668-107">The following code examples contain the GetApplicationObject method of the Sample class, implemented as part of an Outlook add-in project.</span></span> <span data-ttu-id="24668-108">每个项目都添加对基于 [Microsoft.Office.Interop.Outlook](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook?redirectedfrom=MSDN&view=outlook-pia) 命名空间的 Outlook 主互操作程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="24668-108">Each project adds a reference to the Outlook Primary Interop Assembly, which is based on the [Microsoft.Office.Interop.Outlook](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook?redirectedfrom=MSDN&view=outlook-pia) namespace.</span></span>

<span data-ttu-id="24668-109">GetApplicationObject 方法使用 .NET Framework 类库中的类，以检查并获取本地计算机上正在运行的任何 Outlook 进程。</span><span class="sxs-lookup"><span data-stu-id="24668-109">The GetApplicationObject method uses classes in the .NET Framework class library to check and obtain any Outlook process running on the local computer.</span></span> <span data-ttu-id="24668-110">它首先使用[Process](https://docs.microsoft.com/dotnet/api/system.diagnostics.process.getprocessesbyname?redirectedfrom=MSDN&view=netframework-4.8#overloads) 类的 [GetProcessesByName](https://docs.microsoft.com/dotnet/api/system.diagnostics.process?redirectedfrom=MSDN&view=netframework-4.8) 方法 [System.Diagnostics](https://docs.microsoft.com/dotnet/api/system.diagnostics?redirectedfrom=MSDN&view=netframework-4.8) 命名空间中获取的本地计算机上的过程组件共享"OUTLOOK"的过程名称的数组。</span><span class="sxs-lookup"><span data-stu-id="24668-110">It first uses the [GetProcessesByName](https://docs.microsoft.com/dotnet/api/system.diagnostics.process.getprocessesbyname?redirectedfrom=MSDN&view=netframework-4.8#overloads) method of the [Process](https://docs.microsoft.com/dotnet/api/system.diagnostics.process?redirectedfrom=MSDN&view=netframework-4.8) class in the [System.Diagnostics](https://docs.microsoft.com/dotnet/api/system.diagnostics?redirectedfrom=MSDN&view=netframework-4.8) namespace to obtain an array of process components on the local computer that share the process name "OUTLOOK".</span></span> <span data-ttu-id="24668-111">GetApplicationObject 使用 Microsoft 语言集成查询 (LINQ)，以检查数组是否包含至少一个 Outlook 进程。</span><span class="sxs-lookup"><span data-stu-id="24668-111">To check whether the array does contain at least one Outlook process, GetApplicationObject uses Microsoft Language Integrated Query (LINQ).</span></span> <span data-ttu-id="24668-112">[System.Linq](https://msdn.microsoft.com/library/bb345746) 命名空间中的 [Enumerable](https://msdn.microsoft.com/library/bb336768) 类提供了一组的方法，包括 [Count](https://msdn.microsoft.com/library/bb357758) 方法，用于实现 [IEnumerable\<T\>](https://msdn.microsoft.com/library/9eekhta0) 泛型接口。</span><span class="sxs-lookup"><span data-stu-id="24668-112">The [Enumerable](https://msdn.microsoft.com/library/bb345746) class in the [System.Linq](https://msdn.microsoft.com/library/bb336768) namespace provides a set of methods, including the [Count](https://msdn.microsoft.com/library/bb357758) method, that implement the [IEnumerable\<T\>](https://msdn.microsoft.com/library/9eekhta0) generic interface.</span></span> <span data-ttu-id="24668-113">由于 [Array](https://msdn.microsoft.com/library/czz5hkty) 类实现 **IEnumerable(T)** 接口，因此 GetApplicationObject 可将 **Count** 方法应用于 **GetProcessesByName** 返回的数组，以检查是否有正在运行的 Outlook 进程。</span><span class="sxs-lookup"><span data-stu-id="24668-113">Because the [Array](https://msdn.microsoft.com/library/czz5hkty) class implements the **IEnumerable(T)** interface, GetApplicationObject can apply the **Count** method to the array returned by **GetProcessesByName** to see whether there is an Outlook process running.</span></span> <span data-ttu-id="24668-114">如果有，GetApplicationObject 便会使用 [System.Runtime.InteropServices](https://msdn.microsoft.com/library/9esea608\(v=office.15\)) 命名空间中 [Marshal](https://msdn.microsoft.com/library/asx0thw2) 类的 [GetActiveObject](https://msdn.microsoft.com/library/xt620x09) 方法来获取相应 Outlook 实例，并将相应对象强制转换为 Outlook [Application](https://msdn.microsoft.com/library/bb646615\(v=office.15\)) 对象。</span><span class="sxs-lookup"><span data-stu-id="24668-114">If there is, GetApplicationObject uses the [GetActiveObject](https://msdn.microsoft.com/library/xt620x09) method of the [Marshal](https://msdn.microsoft.com/library/asx0thw2) class in the [System.Runtime.InteropServices](https://msdn.microsoft.com/library/9esea608\(v=office.15\)) namespace to obtain that instance of Outlook, and casts that object to an Outlook [Application](https://msdn.microsoft.com/library/bb646615\(v=office.15\)) object.</span></span>

<span data-ttu-id="24668-115">如果本地计算机未运行 Outlook，GetApplicationObject 便会新建 Outlook 实例，使用 [NameSpace](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook.namespace?redirectedfrom=MSDN&view=outlook-pia) 对象的 [Logon(Object, Object, Object, Object)](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook._namespace.logon?redirectedfrom=MSDN&view=outlook-pia#Microsoft_Office_Interop_Outlook__NameSpace_Logon_System_Object_System_Object_System_Object_System_Object_) 方法登录默认配置文件，并返回这一新 Outlook 实例。</span><span class="sxs-lookup"><span data-stu-id="24668-115">If Outlook is not running on the local computer, GetApplicationObject creates a new instance of Outlook, uses the [Logon(Object, Object, Object, Object)](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook._namespace.logon?redirectedfrom=MSDN&view=outlook-pia#Microsoft_Office_Interop_Outlook__NameSpace_Logon_System_Object_System_Object_System_Object_System_Object_) method of the [NameSpace](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook.namespace?redirectedfrom=MSDN&view=outlook-pia) object to sign in to the default profile, and returns that new instance of Outlook.</span></span>

<span data-ttu-id="24668-116">下面先展示了 Visual Basic 代码示例，后展示了 C\# 代码示例。</span><span class="sxs-lookup"><span data-stu-id="24668-116">The following is the Visual Basic code example, followed by the C\# code example.</span></span>

<span data-ttu-id="24668-117">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="24668-117">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the Outlook variable when you import the **Microsoft.Office.Interop.Outlook** namespace.</span></span> <span data-ttu-id="24668-118">不得将 **Imports** 或 **using** 语句直接添加到此代码示例中的函数前面，这两个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="24668-118">The **Imports** or **using** statement must not occur directly before the functions in the code example but must be added before the public Class declaration.</span></span> <span data-ttu-id="24668-119">下面几段代码行展示了如何在 Visual Basic 和 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="24668-119">The following lines of code show how to do the import and assignment in Visual Basic and C\#.</span></span>

```vb
Imports Outlook = Microsoft.Office.Interop.Outlook
```


```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```vb
Imports System.Diagnostics
Imports System.Linq
Imports System.Reflection
Imports System.Runtime.InteropServices
Imports Outlook = Microsoft.Office.Interop.Outlook

Namespace OutlookAddIn2
    Class Sample

        Function GetApplicationObject() As Outlook.Application

            Dim application As Outlook.Application

            ' Check whether there is an Outlook process running.
            If Process.GetProcessesByName("OUTLOOK").Count() > 0 Then

                ' If so, use the GetActiveObject method to obtain the process and cast it to an Application object.
                application = DirectCast(Marshal.GetActiveObject("Outlook.Application"), Outlook.Application)
            Else

                ' If not, create a new instance of Outlook and sign in to the default profile.
                application = New Outlook.Application()
                Dim ns As Outlook.NameSpace = application.GetNamespace("MAPI")
                ns.Logon("", "", Missing.Value, Missing.Value)
                ns = Nothing
            End If

            ' Return the Outlook Application object.
            Return application
        End Function

    End Class
End Namespace
```


```csharp
using System;
using System.Diagnostics;
using System.Linq;
using System.Reflection;
using System.Runtime.InteropServices;
using Outlook = Microsoft.Office.Interop.Outlook;

namespace OutlookAddIn1
{
    class Sample
    {
        Outlook.Application GetApplicationObject()
        {

            Outlook.Application application = null;

            // Check whether there is an Outlook process running.
            if (Process.GetProcessesByName("OUTLOOK").Count() > 0)
            {

                // If so, use the GetActiveObject method to obtain the process and cast it to an Application object.
                application = Marshal.GetActiveObject("Outlook.Application") as Outlook.Application;
            }
            else
            {

                // If not, create a new instance of Outlook and sign in to the default profile.
                application = new Outlook.Application();
                Outlook.NameSpace nameSpace = application.GetNamespace("MAPI");
                nameSpace.Logon("", "", Missing.Value, Missing.Value);
                nameSpace = null;
            }

            // Return the Outlook Application object.
            return application;
        }

    }
}
```

## <a name="see-also"></a><span data-ttu-id="24668-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="24668-120">See also</span></span>

- [<span data-ttu-id="24668-121">会话</span><span class="sxs-lookup"><span data-stu-id="24668-121">Sessions</span></span>](sessions.md)

