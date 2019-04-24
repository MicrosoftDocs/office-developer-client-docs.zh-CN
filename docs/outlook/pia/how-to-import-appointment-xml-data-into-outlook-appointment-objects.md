---
title: 将约会 XML 数据导入 Outlook 约会对象
TOCTitle: Import appointment XML data into Outlook appointment objects
ms:assetid: 166a648a-1c48-4984-8889-a7614cc277b1
ms:mtpsurl: https://msdn.microsoft.com/library/Ff462092(v=office.15)
ms:contentKeyID: 55119821
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 0af86772fced3e69d1d28cf8d98a544e3b4d90d2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32320060"
---
# <a name="import-appointment-xml-data-into-outlook-appointment-objects"></a>将约会 XML 数据导入 Outlook 约会对象

本主题展示了如何读取 XML 格式的约会数据，将此类数据保存到默认日历的 Outlook [AppointmentItem](https://msdn.microsoft.com/library/bb645611\(v=office.15\)) 对象中，再以数组形式返回这些约会对象。

## <a name="example"></a>示例

> [!NOTE] 
> Helmut Obertanner 提供了下面的代码示例。 Helmut 拥有 Visual Studio Office 开发人员工具和 Outlook 方面的专业知识。 


下面的代码示例包含 Sample 类的 CreateAppointmentsFromXml 方法（作为 Outlook 加载项项目的一部分实现）。 每个项目都添加对基于 [Microsoft.Office.Interop.Outlook](https://msdn.microsoft.com/library/bb610835\(v=office.15\)) 命名空间的 Outlook 主互操作程序集的引用。

CreateAppointmentsFromXml 方法接受两个输入参数：

  - application 是受信任的 Outlook [Application](https://msdn.microsoft.com/library/bb646615\(v=office.15\)) 对象。

  - xml 是 XML 字符串或表示有效 XML 文件的路径的字符串。出于对以下代码示例的目的考虑，XML 使用下列 XML 标记分隔约会数据：
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>约会数据</p></th>
    <th><p>分隔 XML 标记</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>整个约会数据集</p></td>
    <td><p>appointments</p></td>
    </tr>
    <tr class="even">
    <td><p>约会集中的每个约会</p></td>
    <td><p>appointment</p></td>
    </tr>
    <tr class="odd">
    <td><p>约会的开始时间</p></td>
    <td><p>starttime</p></td>
    </tr>
    <tr class="even">
    <td><p>约会的结束时间</p></td>
    <td><p>endtime</p></td>
    </tr>
    <tr class="odd">
    <td><p>约会标题</p></td>
    <td><p>subject</p></td>
    </tr>
    <tr class="even">
    <td><p>约会位置</p></td>
    <td><p>location</p></td>
    </tr>
    <tr class="odd">
    <td><p>约会详细信息</p></td>
    <td><p>body</p></td>
    </tr>
    </tbody>
    </table>


下面的代码示例展示了 *xml* 参数的输入数据。

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

CreateAppointmentsFromXml 方法使用 XML 文档对象模型 (DOM) 的 Microsoft COM 实现来加载和处理 xml 提供的 XML 数据。CreateAppointmentsFromXml 首先检查 xml 指定的 XML 数据源是否有效。如果有效，则它将数据加载到 XML 文档 [DOMDocument](https://msdn.microsoft.com/library/ms756987\(v=office.15\)) 中。否则，CreateAppointmentsFromXml 将引发异常。有关 XML DOM 的详细信息，请参阅 [DOM](https://msdn.microsoft.com/library/ms766487\(v=office.15\))。

对于 XML 数据中由 appointment 标记分隔的每个约会子节点，CreateAppointmentsFromXml 查找特定标记，使用 DOM 提取数据，并将数据分配给 **AppointmentItem** 对象的相应属性：[Start](https://msdn.microsoft.com/library/bb647263\(v=office.15\))、[End](https://msdn.microsoft.com/library/bb623715\(v=office.15\))、[Subject](https://msdn.microsoft.com/library/bb611653\(v=office.15\))、[Location](https://msdn.microsoft.com/library/bb608946\(v=office.15\)) 和 [Body](https://msdn.microsoft.com/library/bb644880\(v=office.15\))。 然后，CreateAppointmentsFromXml 将约会保存到默认日历。

CreateAppointmentsFromXml 使用 [System.Collections.Generic](https://docs.microsoft.com/dotnet/api/system.collections.generic?view=netframework-4.7.2) 命名空间中 [List\<T\>](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1?view=netframework-4.7.2) 类的 [Add](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.add?view=netframework-4.7.2) 方法，以聚合这些 AppointmentItem 对象。 当此方法处理了 XML 数据中的所有约会后，它便会以数组形式返回 AppointmentItem 对象。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **Imports** 或 **using** 语句直接添加到此代码示例中的函数前面，这两个语句必须后跟公共类声明。 下面几段代码行展示了如何在 Visual Basic 和 C\# 中执行导入和分配操作。


```vb
Imports Outlook = Microsoft.Office.Interop.Outlook
```



```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```

下面先展示了 Visual Basic 代码示例，后展示了 C\# 代码示例。



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

## <a name="see-also"></a>另请参阅

- [约会](appointments.md)

