---
title: 枚举 （OneNote 开发人员参考 （英文）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 62912d6e-c39e-4f8b-8cdb-ae9b6376cbc0
description: 本主题介绍 OneNote 2013 对象模型中的枚举。
ms.openlocfilehash: ccd75843326ea5942aa80d02246e59e92331a7d2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774155"
---
# <a name="enumerations-onenote-developer-reference"></a>枚举 （OneNote 开发人员参考 （英文）

本主题介绍 OneNote 2013 对象模型中的枚举。
  
## <a name="createfiletype"></a>CreateFileType
<a name="odc_CreateFileType"> </a>

传递给**OpenHierarchy**方法时，指定要创建对象的类型，如果有路径传递给方法如果尚不存在。 
  
|**成员**|**值**|**说明**|
|:-----|:-----|:-----|
|**cftNone** <br/> |0  <br/> |创建没有新的对象。  <br/> |
|**cftNotebook** <br/> |1  <br/> |使用指定的名称和位置创建笔记本。  <br/> |
|**cftFolder** <br/> |2  <br/> |使用指定的名称和位置创建一个分区组。  <br/> |
|**cftSection** <br/> |3  <br/> |使用指定的名称和位置创建一节。  <br/> |
   
## <a name="docklocation"></a>DockLocation
<a name="odc_CreateFileType"> </a>

通过使用[窗口](window-interfaces-onenote.md)界面指示 OneNote 2013 窗口的停靠的位置。 当设置为**DockedLocation**属性，指定要将停靠的 OneNote 窗口的位置。 此枚举 's new in OneNote 2013。 
  
|**成员**|**值**|**说明**|
|:-----|:-----|:-----|
|**dlDefault** <br/> |-1  <br/> |OneNote 窗口在桌面上固定在默认位置。  <br/> |
|**dlLeft** <br/> |1  <br/> |OneNote 窗口停靠在左侧的桌面。  <br/> |
|**dlRight** <br/> |2  <br/> |OneNote 窗口停靠在右侧的桌面。  <br/> |
|**dlTop** <br/> |3  <br/> |OneNote 窗口停靠在桌面的顶部。  <br/> |
|**dlBottom** <br/> |4  <br/> |OneNote 窗口停靠在桌面底部。  <br/> |
   
## <a name="filinglocation"></a>FilingLocation
<a name="odc_CreateFileType"> </a>

传递给**SetFilingLocation**方法时，指定的内容类型归档位置设置为内容类型发送到 OneNote 时。 此枚举 's new in OneNote 2013。 
  
|**成员**|**值**|**说明**|
|:-----|:-----|:-----|
|**flEMail** <br/> |0  <br/> |将其中归 Outlook 电子邮件设置。  <br/> |
|**flContacts** <br/> |1  <br/> |Outlook 联系人将表示其中的设置。  <br/> |
|**flTasks** <br/> |2  <br/> |将其中归 Outlook 任务的设置。  <br/> |
|**flMeetings** <br/> |3  <br/> |将其中归 Outlook 会议的设置。  <br/> |
|**flWebContent** <br/> |4  <br/> |将其中归 Internet Explorer 内容的设置。  <br/> |
|**flPrintOuts** <br/> |5  <br/> |从 OneNote 打印机的打印输出将字段其中的设置。  <br/> |
   
## <a name="filinglocationtype"></a>FilingLocationType
<a name="odc_CreateFileType"> </a>

传递给**SetFilingLocation**方法时，指定其中发送到 OneNote 的内容的存档。 此枚举 's new in OneNote 2013。 
  
|**成员**|**值**|**说明**|
|:-----|:-----|:-----|
|**fltNamedSectionNewPage** <br/> |0  <br/> |设置存档在指定节中的新页面上的内容。  <br/> |
|**fltCurrentSectionNewPage** <br/> |1  <br/> |设置存档在当前节中的新页面上的内容。  <br/> |
|**fltCurrentPage** <br/> |2  <br/> |设置存档当前页上的内容。  <br/> |
|**fltNamedPage** <br/> |4  <br/> |设置存档在指定的页上的内容。  <br/> |
   
## <a name="hierarchyelement"></a>HierarchyElement
<a name="odc_CreateFileType"> </a>

分配给[IQuickFilingDialog](quick-filing-dialog-box-interfaces-onenote.md)接口的**TreeDepth**属性时，指定要显示快速归档对话框中呈现时的 OneNote 树的深度。 传递给**IQuickFilingDialog**对象的**添加按钮**方法时，引用 OneNote 层次结构中的特定元素。 此枚举 's new in OneNote 2013。 
  
|**成员**|**值**|**说明**|
|:-----|:-----|:-----|
|**heNone** <br/> |0  <br/> |是指没有元素。  <br/> |
|**heNotebooks** <br/> |1  <br/> |指笔记本元素。  <br/> |
|**heSectionGroups** <br/> |2  <br/> |指节组元素。  <br/> |
|**heSections** <br/> |4  <br/> |指节元素。  <br/> |
|**hePages** <br/> |8  <br/> |引用页面元素。  <br/> |
   
## <a name="hierarchyscope"></a>HierarchyScope
<a name="odc_HierarchyScope"> </a>

传递给**GetHierarchy**方法时，指定要获取笔记本节点层次结构中的最低级别。 
  
|**成员**|**值**|**说明**|
|:-----|:-----|:-----|
|**hsSelf** <br/> |0  <br/> |获取刚刚的开始节点指定和任何后代。  <br/> |
|**hsChildren** <br/> |1  <br/> |获取高或较低的小节组中的直接子节点的开始节点，并没有后代。  <br/> |
|**hsNotebooks** <br/> |2  <br/> |获取根的开始节点下的所有笔记本。  <br/> |
|**hsSections** <br/> |3  <br/> |获取分区组和小节组中包括的节的开始节点之下的所有节。  <br/> |
|**hsPages** <br/> |4  <br/> |获取在分区组和小节组包括所有页面的开始节点之下的所有页面。  <br/> |
   
## <a name="newpagestyle"></a>NewPageStyle
<a name="odc_HierarchyScope"> </a>

传递给**CreateNewPage**方法时，指定新的页面的样式。 
  
|**成员**|**值**|**说明**|
|:-----|:-----|:-----|
|**npsDefault** <br/> |0  <br/> |创建具有默认页上样式一页。  <br/> |
|**npsBlankPageWithTitle** <br/> |1  <br/> |创建空白页具有一个标题。  <br/> |
|**npsBlankPageNoTitle** <br/> |2  <br/> |创建一个包含没有标题的空白页。  <br/> |
   
## <a name="notebookfilterouttype"></a>NotebookFilterOutType
<a name="odc_HierarchyScope"> </a>

传递给**QFD**对象的**NotebookFilterOut**方法时，指定哪些笔记本，以显示 QFD 框中呈现时。 
  
|**成员**|**值**|**说明**|
|:-----|:-----|:-----|
|**nfoLocal** <br/> |1  <br/> |允许仅本地笔记本。  <br/> |
|**nfoNetwork** <br/> |2  <br/> |允许 UNC 或 SharePoint 笔记本。  <br/> |
|**nfoWeb** <br/> |4  <br/> |允许 OneDrive 笔记本。  <br/> |
|**nfoNoWacUrl** <br/> |8  <br/> |任何笔记本中没有 web 客户端的位置。  <br/> |
   
## <a name="pageinfo-updated-for-onenote-2013"></a>PageInfo （OneNote 2013 的更新）
<a name="odc_PageInfo"> </a>

传递给**GetPageContent**方法时，指定要返回与页面内容的信息的类型。 
  
|**成员**|**值**|**说明**|
|:-----|:-----|:-----|
|**piBasic** <br/> |0  <br/> |返回仅基本页面内容，而不选择标记、 二进制数据对象和二进制数据对象的文件类型。 这是标准的值，以传递。  <br/> |
|**piBinaryData** <br/> |1  <br/> |返回页面上没有选定内容标记，但与所有二进制数据的内容。  <br/> |
|**piSelection** <br/> |2  <br/> |返回页面与所选内容标记中，但没有二进制数据的内容。  <br/> |
|**piBinaryDataSelection** <br/> |3  <br/> |返回页面与所选内容标记和所有二进制数据的内容。  <br/> |
|**piFileType** <br/> |4  <br/> |返回页面与文件二进制数据对象的类型信息的内容。  <br/> |
|**piBinaryDataFileType** <br/> |5  <br/> |返回页面上的内容与为二进制数据对象和二进制数据对象的文件类型信息  <br/> |
|**piSelectionFileType** <br/> |6  <br/> |返回页面与二进制数据的选定内容标记和文件类型信息的内容。  <br/> |
|**piAll** <br/> |7  <br/> |返回所有页面内容。  <br/> |
   
## <a name="publishformat"></a>PublishFormat
<a name="odc_PublishFormat"> </a>

传递给**发布**方法时，指定将在其中显示发布页上的格式。 
  
|**成员**|**值**|**说明**|
|:-----|:-----|:-----|
|**pfOneNote** <br/> |0  <br/> |已发布的网页为.one 格式。  <br/> |
|**pfOneNotePackage** <br/> |1  <br/> |已发布的网页是.onepkg 格式。  <br/> |
|**pfMHTML** <br/> |2  <br/> |.Mht 格式的已发布的网页。  <br/> |
|**pfPDF** <br/> |3  <br/> |已发布的网页为.pdf 格式。  <br/> |
|**pfXPS** <br/> |4  <br/> |.Xps 格式的已发布的网页。  <br/> |
|**pfWord** <br/> |5  <br/> |已发布的网页是.doc 或.docx 格式。  <br/> |
|**pfEMF** <br/> |6  <br/> |增强型图元文件 (.emf) 格式的已发布的网页。  <br/> |
|**pfHTML** <br/> |7  <br/> |已发布的网页是.html 格式。 此成员 's new in OneNote 2013。  <br/> |
|**pfOneNote2007** <br/> |8  <br/> |发布的页面处于 2007年.one 格式。 此成员 's new in OneNote 2013。  <br/> |
   
## <a name="recentresulttype"></a>RecentResultType
<a name="odc_RecentResultType"> </a>

传递给**IQuickFilingDialog**对象的**SetRecentResults**方法时，指定哪些最近的结果列表以显示快速归档对话框中呈现时。 最新的结果列表用于跟踪的一组用户在快速归档对话框中选择的 OneNote 位置。 有 OneNote 2013 中跟踪归档、 搜索和链接操作的三个新结果列表。 此枚举 's new in OneNote 2013。 
  
|**成员**|**值**|**说明**|
|:-----|:-----|:-----|
|**rrtNone** <br/> |0  <br/> |设置要呈现没有新结果列表。  <br/> |
|**rrtFiling** <br/> |1  <br/> |设置该"存档"新结果列表呈现。  <br/> |
|**rrtSearch** <br/> |2  <br/> |设置要呈现的"搜索"新结果列表。  <br/> |
|**rrtLinks** <br/> |3  <br/> |设置要呈现的"链接"新结果列表。  <br/> |
   
## <a name="speciallocation"></a>SpecialLocation
<a name="odc_SpecialLocation"> </a>

传递给**GetSpecialLocation**方法时，指定要获取的特殊位置路径。 
  
|**成员**|**值**|**说明**|
|:-----|:-----|:-----|
|**slBackupFolder** <br/> |0  <br/> |获取对备份文件夹的文件夹位置的路径。  <br/> |
|**slUnfiledNotesSection** <br/> |1  <br/> |获取未归档笔记文件夹位置的路径。  <br/> |
|**slDefaultNotebookFolder** <br/> |2  <br/> |获取默认笔记本文件夹位置的路径。  <br/> |
   
## <a name="treecollapsedstatetype"></a>TreeCollapsedStateType
<a name="odc_SpecialLocation"> </a>

传递给**QFD**对象的**TreeCollapsedState**方法时，指定是否应展开或折叠的层次结构树。 
  
|**成员**|**值**|**说明**|
|:-----|:-----|:-----|
|**tcsExpanded** <br/> |0  <br/> |设置要扩展的层次结构树。  <br/> |
|**tcsCollapsed** <br/> |1  <br/> |设置要折叠的层次结构树。  <br/> |
   
## <a name="xmlschema-updated-for-onenote-2013"></a>XMLSchema （OneNote 2013 的更新）
<a name="odc_SpecialLocation"> </a>

在传递给以下方法之一，指定要使用的 OneNote XML 架构的版本：
  
- **OneNote15.Application.GetPageContent**
    
- **OneNote15.Application.FindMeta**
    
- **OneNote15.Application.FindPages**
    
- **OneNote15.Application.GetHierarchy**
    
- **OneNote15.Application.GetPageContent**
    
- **OneNote15.Application.UpdateHierarchy**
    
- **OneNote15.Application.UpdatePageContent**
    
|**成员**|**值**|**说明**|
|:-----|:-----|:-----|
|**xs2007** <br/> |0  <br/> |引用的 OneNote 2007 架构。  <br/> |
|**xs2010** <br/> |1  <br/> |引用的 OneNote 2010 架构。  <br/> |
|**xs2013** <br/> |2  <br/> |引用 OneNote 2013 架构。  <br/> |
|**xsCurrent** <br/> |2  <br/> |引用当前的 OneNote 版本的架构。  <br/> <br/>**注意**： 我们不建议使用**xsCurrent**在大多数情况下，因为这可能导致与 OneNote 的未来版本的兼容性问题。 而不是指定您的应用程序生成处理，如 xs2013 架构的版本。           |
   
## <a name="see-also"></a>另请参阅

- [OneNote 开发人员参考](onenote-developer-reference.md)

