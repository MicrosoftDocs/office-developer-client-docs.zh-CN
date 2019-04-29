---
title: 枚举 (OneNote 开发人员参考)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 62912d6e-c39e-4f8b-8cdb-ae9b6376cbc0
description: 本主题介绍了 OneNote 2013 对象模型中的枚举。
ms.openlocfilehash: 3338e444e5b0bfd0239e363c3161aeb1914b2d53
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410334"
---
# <a name="enumerations-onenote-developer-reference"></a>枚举 (OneNote 开发人员参考)

本主题介绍了 OneNote 2013 对象模型中的枚举。
  
## <a name="createfiletype"></a>CreateFileType
<a name="odc_CreateFileType"> </a>

传递给**OpenHierarchy**方法时, 如果传递给方法的路径尚不存在, 则指定要创建的对象的类型 (如果有)。 
  
|**成员**|**值**|**说明**|
|:-----|:-----|:-----|
|**cftNone** <br/> |0  <br/> |不创建新对象。  <br/> |
|**cftNotebook** <br/> |1  <br/> |使用指定的名称和位置创建笔记本。  <br/> |
|**cftFolder** <br/> |双面  <br/> |使用指定的名称和位置创建分区组。  <br/> |
|**cftSection** <br/> |第三章  <br/> |使用指定的名称和位置创建一个分区。  <br/> |
   
## <a name="docklocation"></a>DockLocation
<a name="odc_CreateFileType"> </a>

使用[窗口](window-interfaces-onenote.md)界面指示 OneNote 2013 窗口的停靠位置。 设置为**DockedLocation**属性时, 指定要停靠 OneNote 窗口的位置。 此枚举是 OneNote 2013 中的新枚举。 
  
|**成员**|**值**|**说明**|
|:-----|:-----|:-----|
|**dlDefault** <br/> |-1  <br/> |OneNote 窗口停靠在桌面上的默认位置。  <br/> |
|**dlLeft** <br/> |1  <br/> |OneNote 窗口停靠在桌面的左侧。  <br/> |
|**dlRight** <br/> |双面  <br/> |OneNote 窗口停靠在桌面上的右侧。  <br/> |
|**dlTop** <br/> |第三章  <br/> |OneNote 窗口停靠在桌面的顶部。  <br/> |
|**dlBottom** <br/> |4  <br/> |OneNote 窗口停靠在桌面的底部。  <br/> |
   
## <a name="filinglocation"></a>FilingLocation
<a name="odc_CreateFileType"> </a>

传递给**SetFilingLocation**方法时, 指定在将内容类型发送到 OneNote 时为其设置了存档位置的内容类型。 此枚举是 OneNote 2013 中的新枚举。 
  
|**成员**|**值**|**说明**|
|:-----|:-----|:-----|
|**flEMail** <br/> |0  <br/> |设置 Outlook 电子邮件的存档位置。  <br/> |
|**flContacts** <br/> |1  <br/> |设置 Outlook 联系人的存档位置。  <br/> |
|**flTasks** <br/> |双面  <br/> |设置 Outlook 任务的存档位置。  <br/> |
|**flMeetings** <br/> |第三章  <br/> |设置将在其中存档 Outlook 会议的位置。  <br/> |
|**flWebContent** <br/> |4  <br/> |设置将在其中存档 Internet Explorer 内容的位置。  <br/> |
|**flPrintOuts** <br/> |5  <br/> |设置将存档 OneNote 打印机中的打印输出的位置。  <br/> |
   
## <a name="filinglocationtype"></a>FilingLocationType
<a name="odc_CreateFileType"> </a>

传递给**SetFilingLocation**方法时, 指定要将发送到 OneNote 的内容存档到何处。 此枚举是 OneNote 2013 中的新枚举。 
  
|**成员**|**值**|**说明**|
|:-----|:-----|:-----|
|**fltNamedSectionNewPage** <br/> |0  <br/> |设置要在指定分区中的新页面上存档的内容。  <br/> |
|**fltCurrentSectionNewPage** <br/> |1  <br/> |设置要在当前节中的新页面上存档的内容。  <br/> |
|**fltCurrentPage** <br/> |双面  <br/> |设置要在当前页上存档的内容。  <br/> |
|**fltNamedPage** <br/> |4  <br/> |设置要在指定页面上存档的内容。  <br/> |
   
## <a name="hierarchyelement"></a>HierarchyElement
<a name="odc_CreateFileType"> </a>

当分配给[IQuickFilingDialog](quick-filing-dialog-box-interfaces-onenote.md)接口的**TreeDepth**属性时, 指定在呈现 "快速存档" 对话框时要显示的 OneNote 树的深度。 当传递给**IQuickFilingDialog**对象的**AddButton**方法时, 会引用 OneNote 层次结构中的某些元素。 此枚举是 OneNote 2013 中的新枚举。 
  
|**成员**|**值**|**说明**|
|:-----|:-----|:-----|
|**heNone** <br/> |0  <br/> |指的不是元素。  <br/> |
|**heNotebooks** <br/> |1  <br/> |指笔记本元素。  <br/> |
|**heSectionGroups** <br/> |双面  <br/> |引用节组元素。  <br/> |
|**heSections** <br/> |4  <br/> |引用节元素。  <br/> |
|**hePages** <br/> |utf-8  <br/> |引用页面元素。  <br/> |
   
## <a name="hierarchyscope"></a>HierarchyScope
<a name="odc_HierarchyScope"> </a>

传递给**GetHierarchy**方法时, 指定要在笔记本节点层次结构中获取的最低级别。 
  
|**成员**|**值**|**说明**|
|:-----|:-----|:-----|
|**hsSelf** <br/> |0  <br/> |仅获取指定的开始节点, 不获取后代。  <br/> |
|**hsChildren** <br/> |1  <br/> |获取开始节点的直接子节点, 而在更高或较低的子节组中不获取后代。  <br/> |
|**hsNotebooks** <br/> |双面  <br/> |获取开始节点下的所有笔记本或根。  <br/> |
|**hsSections** <br/> |第三章  <br/> |获取开始节点下的所有节, 包括节组和节组中的节。  <br/> |
|**hsPages** <br/> |4  <br/> |获取开始节点下的所有页面, 包括节组和子节组中的所有页面。  <br/> |
   
## <a name="newpagestyle"></a>NewPageStyle
<a name="odc_HierarchyScope"> </a>

传递给**CreateNewPage**方法时, 指定新页面的样式。 
  
|**成员**|**值**|**说明**|
|:-----|:-----|:-----|
|**npsDefault** <br/> |0  <br/> |创建具有默认页面样式的页面。  <br/> |
|**npsBlankPageWithTitle** <br/> |1  <br/> |创建一个具有标题的空白页。  <br/> |
|**npsBlankPageNoTitle** <br/> |双面  <br/> |创建没有标题的空白页。  <br/> |
   
## <a name="notebookfilterouttype"></a>NotebookFilterOutType
<a name="odc_HierarchyScope"> </a>

当传递给**QFD**对象的**NotebookFilterOut**方法时, 指定在呈现 QFD 框时要显示的笔记本。 
  
|**成员**|**值**|**说明**|
|:-----|:-----|:-----|
|**nfoLocal** <br/> |1  <br/> |仅允许本地笔记本。  <br/> |
|**nfoNetwork** <br/> |双面  <br/> |允许 UNC 或 SharePoint 笔记本。  <br/> |
|**nfoWeb** <br/> |4  <br/> |允许 OneDrive 笔记本。  <br/> |
|**nfoNoWacUrl** <br/> |utf-8  <br/> |没有 web 客户端的位置中的任何笔记本。  <br/> |
   
## <a name="pageinfo-updated-for-onenote-2013"></a>PageInfo (针对 OneNote 2013 进行了更新)
<a name="odc_PageInfo"> </a>

传递给**GetPageContent**方法时, 指定要与页面内容一起返回的信息的类型。 
  
|**成员**|**值**|**说明**|
|:-----|:-----|:-----|
|**piBasic** <br/> |0  <br/> |仅返回基本页面内容, 不包含选择标记、二进制数据对象的文件类型和二进制数据对象。 这是要传递的标准值。  <br/> |
|**piBinaryData** <br/> |1  <br/> |返回不带选择标记但包含所有二进制数据的页面内容。  <br/> |
|**piSelection** <br/> |双面  <br/> |使用选择标记返回页面内容, 但不返回二进制数据。  <br/> |
|**piBinaryDataSelection** <br/> |第三章  <br/> |返回包含选定标记和所有二进制数据的页面内容。  <br/> |
|**piFileType** <br/> |4  <br/> |返回包含二进制数据对象的文件类型信息的页面内容。  <br/> |
|**piBinaryDataFileType** <br/> |5  <br/> |返回包含二进制数据对象和二进制数据对象的文件类型信息的页面内容  <br/> |
|**piSelectionFileType** <br/> |型  <br/> |返回包含二进制数据的选择标记和文件类型信息的页面内容。  <br/> |
|**piAll** <br/> |步  <br/> |返回所有页面内容。  <br/> |
   
## <a name="publishformat"></a>所用
<a name="odc_PublishFormat"> </a>

传递给**Publish**方法时, 指定发布页面的显示格式。 
  
|**成员**|**值**|**说明**|
|:-----|:-----|:-----|
|**pfOneNote** <br/> |0  <br/> |已发布页面的格式为 .one。  <br/> |
|**pfOneNotePackage** <br/> |1  <br/> |已发布页面的格式为 onepkg。  <br/> |
|**pfMHTML** <br/> |双面  <br/> |已发布页面的格式为 .mht。  <br/> |
|**pfPDF** <br/> |第三章  <br/> |已发布页面的格式为 .pdf。  <br/> |
|**pfXPS** <br/> |4  <br/> |已发布页面的格式为 .xps。  <br/> |
|**pfWord** <br/> |5  <br/> |已发布页面的格式为 .doc 或 .docx。  <br/> |
|**pfEMF** <br/> |型  <br/> |已发布页面位于增强型图元文件 (.emf) 格式中。  <br/> |
|**pfHTML** <br/> |步  <br/> |已发布页面的格式为 .html。 此成员是 OneNote 2013 中的新成员。  <br/> |
|**pfOneNote2007** <br/> |utf-8  <br/> |发布的页面采用2007。一种格式。 此成员是 OneNote 2013 中的新成员。  <br/> |
   
## <a name="recentresulttype"></a>RecentResultType
<a name="odc_RecentResultType"> </a>

当传递给**IQuickFilingDialog**对象的**SetRecentResults**方法时, 指定在呈现快速存档对话框时要显示的最近结果列表。 最近的结果列表用于跟踪用户在 "快速归档" 对话框中选择的一组 OneNote 位置。 OneNote 2013 中有三个最近的结果列表, 用于跟踪存档、搜索和链接操作。 此枚举是 OneNote 2013 中的新枚举。 
  
|**成员**|**值**|**说明**|
|:-----|:-----|:-----|
|**rrtNone** <br/> |0  <br/> |设置没有要呈现的最近结果列表。  <br/> |
|**rrtFiling** <br/> |1  <br/> |设置要呈现的 "存档" 最近结果列表。  <br/> |
|**rrtSearch** <br/> |双面  <br/> |设置要呈现的 "搜索" 最近结果列表。  <br/> |
|**rrtLinks** <br/> |第三章  <br/> |设置要呈现的 "链接" 最近结果列表。  <br/> |
   
## <a name="speciallocation"></a>它
<a name="odc_SpecialLocation"> </a>

传递给**GetSpecialLocation**方法时, 指定要获取的特殊位置路径。 
  
|**成员**|**值**|**说明**|
|:-----|:-----|:-----|
|**slBackupFolder** <br/> |0  <br/> |获取备份文件夹文件夹位置的路径。  <br/> |
|**slUnfiledNotesSection** <br/> |1  <br/> |获取未归档的 "便笺" 文件夹位置的路径。  <br/> |
|**slDefaultNotebookFolder** <br/> |双面  <br/> |获取默认笔记本文件夹位置的路径。  <br/> |
   
## <a name="treecollapsedstatetype"></a>TreeCollapsedStateType
<a name="odc_SpecialLocation"> </a>

当传递给**QFD**对象的**TreeCollapsedState**方法时, 指定是展开还是折叠层次结构树。 
  
|**成员**|**值**|**说明**|
|:-----|:-----|:-----|
|**tcsExpanded** <br/> |0  <br/> |将层次结构树设置为 "展开"。  <br/> |
|**tcsCollapsed** <br/> |1  <br/> |将层次结构树设置为折叠。  <br/> |
   
## <a name="xmlschema-updated-for-onenote-2013"></a>XMLSchema (针对 OneNote 2013 进行了更新)
<a name="odc_SpecialLocation"> </a>

当传递到以下方法之一时, 指定要使用的 OneNote XML 架构的版本:
  
- **OneNote15 GetPageContent**
    
- **OneNote15 FindMeta**
    
- **OneNote15 FindPages**
    
- **OneNote15 GetHierarchy**
    
- **OneNote15 GetPageContent**
    
- **OneNote15 UpdateHierarchy**
    
- **OneNote15 UpdatePageContent**
    
|**成员**|**值**|**说明**|
|:-----|:-----|:-----|
|**xs2007** <br/> |0  <br/> |引用 OneNote 2007 架构。  <br/> |
|**xs2010** <br/> |1  <br/> |引用 OneNote 2010 架构。  <br/> |
|**xs2013** <br/> |双面  <br/> |引用 OneNote 2013 架构。  <br/> |
|**xsCurrent** <br/> |双面  <br/> |引用当前 OneNote 版本的架构。  <br/> <br/>**注意**: 在大多数情况下, 我们不建议使用**xsCurrent** , 因为它可能会导致将来版本的 OneNote 存在兼容性问题。 而是指定您的应用程序生成的架构版本, 如 xs2013。           |
   
## <a name="see-also"></a>另请参阅

- [OneNote 开发人员参考](onenote-developer-reference.md)

