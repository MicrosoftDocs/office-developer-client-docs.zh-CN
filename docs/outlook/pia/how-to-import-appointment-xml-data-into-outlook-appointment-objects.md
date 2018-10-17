---
title: 将约会 XML 数据导入 Outlook 约会对象
TOCTitle: Import appointment XML data into Outlook appointment objects
ms:assetid: 166a648a-1c48-4984-8889-a7614cc277b1
ms:mtpsurl: https://msdn.microsoft.com/library/Ff462092(v=office.15)
ms:contentKeyID: 55119821
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: 22d7e17e208aa67648e2fe785d58bc030b41e001
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25405831"
---
# <a name="import-appointment-xml-data-into-outlook-appointment-objects"></a><span data-ttu-id="b35dc-102">将约会 XML 数据导入 Outlook 约会对象</span><span class="sxs-lookup"><span data-stu-id="b35dc-102">Import Appointment XML Data into Outlook Appointment Objects</span></span>

<span data-ttu-id="b35dc-103">本主题展示了如何读取 XML 格式的约会数据，将此类数据保存到默认日历的 Outlook [AppointmentItem](https://msdn.microsoft.com/library/bb645611\(v=office.15\)) 对象中，再以数组形式返回这些约会对象。</span><span class="sxs-lookup"><span data-stu-id="b35dc-103">This topic shows how to read appointment data formatted in XML, save the data to Microsoft Outlook [AppointmentItem](https://msdn.microsoft.com/library/bb645611\(v=office.15\)) objects in the default calendar, and return the appointment objects in an array.</span></span>

## <a name="example"></a><span data-ttu-id="b35dc-104">示例</span><span class="sxs-lookup"><span data-stu-id="b35dc-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="b35dc-105">Helmut Obertanner 提供了下面的代码示例。</span><span class="sxs-lookup"><span data-stu-id="b35dc-105">Helmut Obertanner provided the following code examples.</span></span> <span data-ttu-id="b35dc-106">Helmut 拥有 Visual Studio Office 开发人员工具和 Outlook 方面的专业知识。</span><span class="sxs-lookup"><span data-stu-id="b35dc-106">Helmut's expertise is in Office Developer Tools for Visual Studio and Outlook.</span></span> 


<span data-ttu-id="b35dc-107">下面的代码示例包含 Sample 类的 CreateAppointmentsFromXml 方法（作为 Outlook 加载项项目的一部分实现）。</span><span class="sxs-lookup"><span data-stu-id="b35dc-107">The following code examples contain the   method of the   class, implemented as part of an Outlook add-in project.</span></span> <span data-ttu-id="b35dc-108">每个项目都添加对基于 [Microsoft.Office.Interop.Outlook](https://msdn.microsoft.com/library/bb610835\(v=office.15\)) 命名空间的 Outlook 主互操作程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="b35dc-108">Each project adds a reference to the Outlook Primary Interop Assembly, which is based on the [Microsoft.Office.Interop.Outlook](https://msdn.microsoft.com/library/bb610835\(v=office.15\)) namespace.</span></span>

<span data-ttu-id="b35dc-109">CreateAppointmentsFromXml 方法接受两个输入参数：</span><span class="sxs-lookup"><span data-stu-id="b35dc-109">The CreateAppointmentsFromXml method accepts two input parameters:</span></span>

  - <span data-ttu-id="b35dc-110">application 是受信任的 Outlook [Application](https://msdn.microsoft.com/library/bb646615\(v=office.15\)) 对象。</span><span class="sxs-lookup"><span data-stu-id="b35dc-110">application is a trusted Outlook [Application](https://msdn.microsoft.com/library/bb646615\(v=office.15\)) object.</span></span>

  - <span data-ttu-id="b35dc-p103">xml 是 XML 字符串或表示有效 XML 文件的路径的字符串。出于对以下代码示例的目的考虑，XML 使用下列 XML 标记分隔约会数据：</span><span class="sxs-lookup"><span data-stu-id="b35dc-p103">xml is either an XML string, or a string that represents a path to a valid XML file. For the purpose of the following code examples, the XML delimits appointment data by using the following XML tags:</span></span>
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p><span data-ttu-id="b35dc-113">约会数据</span><span class="sxs-lookup"><span data-stu-id="b35dc-113">Appointment data</span></span></p></th>
    <th><p><span data-ttu-id="b35dc-114">分隔 XML 标记</span><span class="sxs-lookup"><span data-stu-id="b35dc-114">Delimiting XML tag</span></span></p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="b35dc-115">整个约会数据集</span><span class="sxs-lookup"><span data-stu-id="b35dc-115">Entire set of appointment data</span></span></p></td>
    <td><p><span data-ttu-id="b35dc-116">appointments</span><span class="sxs-lookup"><span data-stu-id="b35dc-116">appointments</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="b35dc-117">约会集中的每个约会</span><span class="sxs-lookup"><span data-stu-id="b35dc-117">Each appointment in the set</span></span></p></td>
    <td><p><span data-ttu-id="b35dc-118">appointment</span><span class="sxs-lookup"><span data-stu-id="b35dc-118">appointment</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="b35dc-119">约会的开始时间</span><span class="sxs-lookup"><span data-stu-id="b35dc-119">Start time of an appointment</span></span></p></td>
    <td><p><span data-ttu-id="b35dc-120">starttime</span><span class="sxs-lookup"><span data-stu-id="b35dc-120">StartTime</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="b35dc-121">约会的结束时间</span><span class="sxs-lookup"><span data-stu-id="b35dc-121">End time of an appointment</span></span></p></td>
    <td><p><span data-ttu-id="b35dc-122">endtime</span><span class="sxs-lookup"><span data-stu-id="b35dc-122">EndTime</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="b35dc-123">约会标题</span><span class="sxs-lookup"><span data-stu-id="b35dc-123">Title of an appointment</span></span></p></td>
    <td><p><span data-ttu-id="b35dc-124">subject</span><span class="sxs-lookup"><span data-stu-id="b35dc-124">subject</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="b35dc-125">约会位置</span><span class="sxs-lookup"><span data-stu-id="b35dc-125">Location of an appointment</span></span></p></td>
    <td><p><span data-ttu-id="b35dc-126">location</span><span class="sxs-lookup"><span data-stu-id="b35dc-126">location</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="b35dc-127">约会详细信息</span><span class="sxs-lookup"><span data-stu-id="b35dc-127">Details of an appointment</span></span></p></td>
    <td><p><span data-ttu-id="b35dc-128">body</span><span class="sxs-lookup"><span data-stu-id="b35dc-128">body</span></span></p></td>
    </tr>
    </tbody>
    </table>


<span data-ttu-id="b35dc-129">下面的代码示例展示了 *xml* 参数的输入数据。</span><span class="sxs-lookup"><span data-stu-id="b35dc-129">The following example shows input data for the  *xml* parameter.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?> 
<appointments>
    <appointment>
        <starttime>2009-06-01T15:00:00</starttime>
        <endtime>2009-06-01T16:15:00</endtime>
        <subject>This is a Test-Appointment</subject>
        <location>At your Desk</location>
        <body>Here is the Bodytext</body>
    </appointment>
    <appointment>
        <starttime>2009-06-01T17:00:00</starttime>
        <endtime>2009-06-01T17:15:00</endtime>
        <subject>This is a second Test-Appointment</subject>
        <location>At your Desk</location>
        <body>Here is the Bodytext</body>
    </appointment>
    <appointment>
        <starttime>2009-06-01T17:00:00</starttime>
        <endtime>2009-06-01T18:15:00</endtime>
        <subject>This is a third Test-Appointment</subject>
        <location>At your Desk</location>
        <body>Here is the Bodytext</body>
    </appointment>
</appointments>
```

<span data-ttu-id="b35dc-p104">CreateAppointmentsFromXml 方法使用 XML 文档对象模型 (DOM) 的 Microsoft COM 实现来加载和处理 xml 提供的 XML 数据。CreateAppointmentsFromXml 首先检查 xml 指定的 XML 数据源是否有效。如果有效，则它将数据加载到 XML 文档 [DOMDocument](https://msdn.microsoft.com/library/ms756987\(v=office.15\)) 中。否则，CreateAppointmentsFromXml 将引发异常。有关 XML DOM 的详细信息，请参阅 [DOM](https://msdn.microsoft.com/library/ms766487\(v=office.15\))。</span><span class="sxs-lookup"><span data-stu-id="b35dc-p104">The CreateAppointmentsFromXml method uses the Microsoft COM implementation of the XML Document Object Model (DOM) to load and process the XML data that xml provides. CreateAppointmentsFromXml first checks whether xml specifies a valid source of XML data. If so, it loads the data into an XML document, [DOMDocument](https://msdn.microsoft.com/library/ms756987\(v=office.15\)). Otherwise, CreateAppointmentsFromXml throws an exception. For more information about the XML DOM, see [DOM](https://msdn.microsoft.com/library/ms766487\(v=office.15\)).</span></span>

<span data-ttu-id="b35dc-135">对于 XML 数据中由 appointment 标记分隔的每个约会子节点，CreateAppointmentsFromXml 查找特定标记，使用 DOM 提取数据，并将数据分配给 **AppointmentItem** 对象的相应属性：[Start](https://msdn.microsoft.com/library/bb647263\(v=office.15\))、[End](https://msdn.microsoft.com/library/bb623715\(v=office.15\))、[Subject](https://msdn.microsoft.com/library/bb611653\(v=office.15\))、[Location](https://msdn.microsoft.com/library/bb608946\(v=office.15\)) 和 [Body](https://msdn.microsoft.com/library/bb644880\(v=office.15\))。</span><span class="sxs-lookup"><span data-stu-id="b35dc-135">For each appointment child node delimited by the appointment tag in the XML data,   looks for specific tags, uses the DOM to extract the data, and assigns the data to corresponding properties of an AppointmentItem object: Start , End , Subject , Location , and Body .</span></span> <span data-ttu-id="b35dc-136">然后，CreateAppointmentsFromXml 将约会保存到默认日历。</span><span class="sxs-lookup"><span data-stu-id="b35dc-136"> then saves the appointment to the default calendar.</span></span>

<span data-ttu-id="b35dc-137">CreateAppointmentsFromXml 使用 [System.Collections.Generic](https://docs.microsoft.com/dotnet/api/system.collections.generic?view=netframework-4.7.2) 命名空间中 [List\<T\>](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1?view=netframework-4.7.2) 类的 [Add](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.add?view=netframework-4.7.2) 方法，以聚合这些 AppointmentItem 对象。</span><span class="sxs-lookup"><span data-stu-id="b35dc-137"> uses the Add method of the List(T) class in the System.Collections.Generic namespace to aggregate these AppointmentItem objects.</span></span> <span data-ttu-id="b35dc-138">当此方法处理了 XML 数据中的所有约会后，它便会以数组形式返回 AppointmentItem 对象。</span><span class="sxs-lookup"><span data-stu-id="b35dc-138">When the method has processed all the appointments in the XML data, it returns the AppointmentItem objects in an array.</span></span>

<span data-ttu-id="b35dc-139">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="b35dc-139">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the   variable when you import the Microsoft.Office.Interop.Outlook namespace.</span></span> <span data-ttu-id="b35dc-140">不得将 **Imports** 或 **using** 语句直接添加到此代码示例中的函数前面，这两个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="b35dc-140">The Imports or using statement must not occur directly before the functions in the code example but must be added before the public   declaration.</span></span> <span data-ttu-id="b35dc-141">下面几段代码行展示了如何在 Visual Basic 和 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="b35dc-141">The following lines of code show how to do the import and assignment in Visual Basic and C#.</span></span>


```vb
Imports Outlook = Microsoft.Office.Interop.Outlook
```



```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```

<span data-ttu-id="b35dc-142">下面先展示了 Visual Basic 代码示例，后展示了 C\# 代码示例。</span><span class="sxs-lookup"><span data-stu-id="b35dc-142">The following is the Visual Basic code example, followed by the C# code example.</span></span>



```vb
Imports System.IO
Imports System.Xml
Imports Outlook = Microsoft.Office.Interop.Outlook

Namespace OutlookAddIn2
    Class Sample
        Function CreateAppointmentsFromXml(ByVal application As Outlook.Application, _
            ByVal xml As String) As Outlook.AppointmentItem()

            Dim appointments As New List(Of Outlook.AppointmentItem)
            Dim xmlDoc As New XmlDocument()

            ' If xml is an XML string, create the XML document directly.
            If xml.StartsWith("<?xml") Then
                xmlDoc.LoadXml(xml)
            ElseIf (File.Exists(xml)) Then
                xmlDoc.Load(xml)
            Else
                Throw New Exception("The input string is not valid XML data or the specified file doesn't exist.")
            End If


            ' Select all appointment nodes under the root appointments node.
            Dim appointmentNodes As XmlNodeList = xmlDoc.SelectNodes("appointments/appointment")

            For Each appointmentNode As XmlNode In appointmentNodes

                ' Create a new AppointmentItem object.
                Dim newAppointment As Outlook.AppointmentItem = _
                    DirectCast(application.CreateItem(Outlook.OlItemType.olAppointmentItem), _
                    Outlook.AppointmentItem)

                ' Loop over all child nodes, check the node name, and import the data into the appointment fields.

                For Each node As XmlNode In appointmentNode.ChildNodes
                    Select Case (node.Name)

                        Case "starttime"
                            newAppointment.Start = DateTime.Parse(node.InnerText)


                        Case "endtime"
                            newAppointment.End = DateTime.Parse(node.InnerText)


                        Case "subject"
                            newAppointment.Subject = node.InnerText


                        Case "location"
                            newAppointment.Location = node.InnerText


                        Case "body"
                            newAppointment.Body = node.InnerText


                    End Select
                Next

                ' Save the item in the default calendar.
                newAppointment.Save()
                appointments.Add(newAppointment)
            Next

            ' Return an array of new appointments.
            Return appointments.ToArray()
        End Function


    End Class
End Namespace
```



```csharp
using System;
using System.Collections.Generic;
using System.IO;
using System.Text;
using System.Xml;
using Outlook = Microsoft.Office.Interop.Outlook;

namespace OutlookAddIn1
{
    class Sample
    {
        Outlook.AppointmentItem[] CreateAppointmentsFromXml(Outlook.Application application, 
            string xml)
        {
            // Create a list of appointment objects.
            List<Outlook.AppointmentItem> appointments = new 
                List<Microsoft.Office.Interop.Outlook.AppointmentItem>();
            XmlDocument xmlDoc = new XmlDocument();

            // If xml is an XML string, create the document directly. 
            if (xml.StartsWith("<?xml"))
            {
                xmlDoc.LoadXml(xml);
            }
            else if (File.Exists(xml))
            {
                xmlDoc.Load(xml);
            }
            else
            {
                throw new Exception(
                    "The input string is not valid XML data or the specified file doesn't exist.");
            }

            // Select all appointment nodes under the root appointments node.
            XmlNodeList appointmentNodes = xmlDoc.SelectNodes("appointments/appointment");
            foreach (XmlNode appointmentNode in appointmentNodes)
            {

                // Create a new AppointmentItem object.
                Outlook.AppointmentItem newAppointment = 
                    (Outlook.AppointmentItem)application.CreateItem(Outlook.OlItemType.olAppointmentItem);

                // Loop over all child nodes, check the node name, and import the data into the 
                // appointment fields.
                foreach (XmlNode node in appointmentNode.ChildNodes)
                {
                    switch (node.Name)
                    {

                        case "starttime":
                            newAppointment.Start = DateTime.Parse(node.InnerText);
                            break;

                        case "endtime":
                            newAppointment.End = DateTime.Parse(node.InnerText);
                            break;

                        case "subject":
                            newAppointment.Subject = node.InnerText;
                            break;

                        case "location":
                            newAppointment.Location = node.InnerText;
                            break;

                        case "body":
                            newAppointment.Body = node.InnerText;
                            break;

                    }
                }

                // Save the item in the default calendar.
                newAppointment.Save();
                appointments.Add(newAppointment);
            }

            // Return an array of new appointments.
            return appointments.ToArray();
        }

    }
}
```

## <a name="see-also"></a><span data-ttu-id="b35dc-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b35dc-143">See also</span></span>

- [<span data-ttu-id="b35dc-144">约会</span><span class="sxs-lookup"><span data-stu-id="b35dc-144">Appointments</span></span>](appointments.md)

