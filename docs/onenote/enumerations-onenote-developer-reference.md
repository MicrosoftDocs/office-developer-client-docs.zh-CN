---
title: '枚举 (OneNote开发人员参考) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 62912d6e-c39e-4f8b-8cdb-ae9b6376cbc0
description: 本主题介绍 OneNote 2013 对象模型中的枚举。
ms.openlocfilehash: 3338e444e5b0bfd0239e363c3161aeb1914b2d53
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410334"
---
# <a name="enumerations-onenote-developer-reference"></a>枚举 (OneNote开发人员参考) 

本主题介绍 OneNote 2013 对象模型中的枚举。
  
## <a name="createfiletype"></a>CreateFileType
<a name="odc_CreateFileType"> </a>

传递给 **OpenHierarchy** 方法时，指定要创建的对象的类型（如果有）（如果传递给该方法的路径尚不存在）。 
  
|**成员**|**值**|**说明**|
|:-----|:-----|:-----|
|**cftNone** <br/> |0  <br/> |不创建新的对象。  <br/> |
|**cftNotebook** <br/> |1  <br/> |使用指定的名称和位置创建笔记本。  <br/> |
|**cftFolder** <br/> |2  <br/> |使用指定的名称和位置创建分区组。  <br/> |
|**cftSection** <br/> |3  <br/> |使用指定的名称和位置创建节。  <br/> |
   
## <a name="docklocation"></a>DockLocation
<a name="odc_CreateFileType"> </a>

使用[Window](window-interfaces-onenote.md)接口指示 OneNote 2013 窗口的固定位置。 设置为 **DockedLocation** 属性时，指定停靠窗口OneNote的位置。 此枚举是 OneNote 2013 中的新增功能。 
  
|**成员**|**值**|**说明**|
|:-----|:-----|:-----|
|**dlDefault** <br/> |-1  <br/> |the OneNote window is docked at the default location on the desktop.  <br/> |
|**dlLeft** <br/> |1  <br/> |the OneNote window is docked on the left side of the desktop.  <br/> |
|**dlRight** <br/> |2  <br/> |the OneNote window is docked on the right side of the desktop.  <br/> |
|**dlTop** <br/> |3  <br/> |the OneNote window is docked at the top of the desktop.  <br/> |
|**dlBottom** <br/> |4   <br/> |the OneNote window is docked at the bottom of the desktop.  <br/> |
   
## <a name="filinglocation"></a>FilingLocation
<a name="odc_CreateFileType"> </a>

当传递到 **SetFilingLocation** 方法时，指定在将内容类型发送到内容类型时设置归档位置OneNote。 此枚举是 OneNote 2013 中的新增功能。 
  
|**成员**|**值**|**说明**|
|:-----|:-----|:-----|
|**flEMail** <br/> |0  <br/> |设置Outlook电子邮件的存档位置。  <br/> |
|**flContacts** <br/> |1  <br/> |设置Outlook的存档位置。  <br/> |
|**flTasks** <br/> |2  <br/> |设置Outlook存档任务的地方。  <br/> |
|**flMeetings** <br/> |3  <br/> |设置Outlook会议地点。  <br/> |
|**flWebContent** <br/> |4   <br/> |设置Internet Explorer内容的存档位置。  <br/> |
|**flPrintOuts** <br/> |5   <br/> |设置从打印机打印OneNote的归档位置。  <br/> |
   
## <a name="filinglocationtype"></a>FilingLocationType
<a name="odc_CreateFileType"> </a>

传递给 **SetFilingLocation** 方法时，指定发送到OneNote存档位置。 此枚举是 OneNote 2013 中的新增功能。 
  
|**成员**|**值**|**说明**|
|:-----|:-----|:-----|
|**fltNamedSectionNewPage** <br/> |0  <br/> |设置要归档到指定节中新页面上的内容。  <br/> |
|**fltCurrentSectionNewPage** <br/> |1  <br/> |设置要归档到当前部分的新页面上的内容。  <br/> |
|**fltCurrentPage** <br/> |2  <br/> |设置当前页面上要归档的内容。  <br/> |
|**fltNamedPage** <br/> |4   <br/> |设置要归档到指定页面上的内容。  <br/> |
   
## <a name="hierarchyelement"></a>HierarchyElement
<a name="odc_CreateFileType"> </a>

当分配给 [IQuickFilingDialog](quick-filing-dialog-box-interfaces-onenote.md)接口的 **TreeDepth** 属性时，指定呈现快速归档对话框时要显示的 OneNote 树的深度。 当传递给 **IQuickFilingDialog** 对象的 **AddButton** 方法时，引用该层次结构中的OneNote元素。 此枚举是 OneNote 2013 中的新增功能。 
  
|**成员**|**值**|**说明**|
|:-----|:-----|:-----|
|**heNone** <br/> |0  <br/> |引用无元素。  <br/> |
|**heNotebooks** <br/> |1  <br/> |引用 Notebook 元素。  <br/> |
|**heSectionGroups** <br/> |2  <br/> |引用 Section Group 元素。  <br/> |
|**heSections** <br/> |4   <br/> |引用 Section 元素。  <br/> |
|**hePages** <br/> |8   <br/> |引用 Page 元素。  <br/> |
   
## <a name="hierarchyscope"></a>HierarchyScope
<a name="odc_HierarchyScope"> </a>

传递给 **GetHierarchy** 方法时，指定要获取的笔记本节点层次结构的最低级别。 
  
|**成员**|**值**|**说明**|
|:-----|:-----|:-----|
|**hsSelf** <br/> |0  <br/> |仅获取指定的开始节点，而无后代。  <br/> |
|**hsChildren** <br/> |1  <br/> |获取开始节点的直接子节点，在较高或较低子组中没有后代。  <br/> |
|**hsNotebooks** <br/> |2  <br/> |获取开始节点或根目录下的所有笔记本。  <br/> |
|**hsSections** <br/> |3  <br/> |获取开始节点下的所有节，包括节组和子组中的节。  <br/> |
|**hsPages** <br/> |4   <br/> |获取开始节点下的所有页面，包括分区组和子组的所有页面。  <br/> |
   
## <a name="newpagestyle"></a>NewPageStyle
<a name="odc_HierarchyScope"> </a>

传递给 **CreateNewPage** 方法时，指定新页面的样式。 
  
|**成员**|**值**|**说明**|
|:-----|:-----|:-----|
|**npsDefault** <br/> |0  <br/> |创建具有默认页面样式的页面。  <br/> |
|**npsBlankPageWithTitle** <br/> |1  <br/> |创建一个包含标题的空白页。  <br/> |
|**npsBlankPageNoTitle** <br/> |2  <br/> |创建没有标题的空白页。  <br/> |
   
## <a name="notebookfilterouttype"></a>NotebookFilterOutType
<a name="odc_HierarchyScope"> </a>

当传递给 **QFD** **对象的 NotebookFilterOut** 方法时，指定呈现 QFD 框时要显示的笔记本。 
  
|**成员**|**值**|**说明**|
|:-----|:-----|:-----|
|**nfoLocal** <br/> |1  <br/> |仅允许本地笔记本。  <br/> |
|**nfoNetwork** <br/> |2  <br/> |允许 UNC 或SharePoint笔记本。  <br/> |
|**nfoWeb** <br/> |4   <br/> |允许OneDrive笔记本。  <br/> |
|**nfoNoWacUrl** <br/> |8   <br/> |位置中没有 Web 客户端的任何笔记本。  <br/> |
   
## <a name="pageinfo-updated-for-onenote-2013"></a>PageInfo (2013 OneNote更新) 
<a name="odc_PageInfo"> </a>

传递给 **GetPageContent** 方法时，指定要与页面内容一起返回的信息的类型。 
  
|**成员**|**值**|**说明**|
|:-----|:-----|:-----|
|**piBasic** <br/> |0  <br/> |仅返回基本页面内容，而不返回选择标记、二进制数据对象和二进制数据对象的文件类型。 这是要传递的标准值。  <br/> |
|**piBinaryData** <br/> |1  <br/> |返回没有选择标记但包含所有二进制数据的页面内容。  <br/> |
|**piSelection** <br/> |2  <br/> |返回包含选择标记的页面内容，但没有二进制数据。  <br/> |
|**piBinaryDataSelection** <br/> |3  <br/> |返回包含选择标记以及所有二进制数据的页面内容。  <br/> |
|**piFileType** <br/> |4   <br/> |返回包含二进制数据对象的文件类型信息的页面内容。  <br/> |
|**piBinaryDataFileType** <br/> |5   <br/> |返回包含二进制数据对象和二进制数据对象的文件类型信息的页面内容  <br/> |
|**piSelectionFileType** <br/> |6   <br/> |返回包含二进制数据的选择标记和文件类型信息的页面内容。  <br/> |
|**piAll** <br/> |7   <br/> |返回所有页面内容。  <br/> |
   
## <a name="publishformat"></a>PublishFormat
<a name="odc_PublishFormat"> </a>

传递给 Publish **方法** 时，指定发布页面的显示格式。 
  
|**成员**|**值**|**说明**|
|:-----|:-----|:-----|
|**pfOneNote** <br/> |0  <br/> |已发布页面采用 .one 格式。  <br/> |
|**pfOneNotePackage** <br/> |1  <br/> |已发布页面采用 .onepkg 格式。  <br/> |
|**pfMHTML** <br/> |2  <br/> |已发布页面采用 .mht 格式。  <br/> |
|**pfPDF** <br/> |3  <br/> |已发布页面采用.pdf格式。  <br/> |
|**pfXPS** <br/> |4   <br/> |已发布页面采用 .xps 格式。  <br/> |
|**pfWord** <br/> |5   <br/> |已发布页面采用 .doc 或 .docx 格式。  <br/> |
|**pfEMF** <br/> |6   <br/> |已发布页面采用增强图元文件 (.emf) 格式。  <br/> |
|**pfHTML** <br/> |7   <br/> |已发布页面采用.html格式。 此成员是 OneNote 2013 中的新增成员。  <br/> |
|**pfOneNote2007** <br/> |8   <br/> |已发布页面采用 2007 .one 格式。 此成员是 OneNote 2013 中的新增成员。  <br/> |
   
## <a name="recentresulttype"></a>RecentResultType
<a name="odc_RecentResultType"> </a>

当传递给 **IQuickFilingDialog** 对象的 **SetRecentResults** 方法时，指定呈现"快速归档"对话框时要显示的最近结果列表。 最近的结果列表用于跟踪用户OneNote"快速归档"对话框中选择的位置集。 2013 年 3 月OneNote三个跟踪归档、搜索和链接操作的结果列表。 此枚举是 OneNote 2013 中的新增功能。 
  
|**成员**|**值**|**说明**|
|:-----|:-----|:-----|
|**rrtNone** <br/> |0  <br/> |设置要呈现的最近结果列表。  <br/> |
|**rrtFiling** <br/> |1  <br/> |设置要呈现的"归档"最近结果列表。  <br/> |
|**rrtSearch** <br/> |2  <br/> |设置要呈现的"搜索"最近结果列表。  <br/> |
|**rrtLinks** <br/> |3  <br/> |设置要呈现的"Links"最近结果列表。  <br/> |
   
## <a name="speciallocation"></a>SpecialLocation
<a name="odc_SpecialLocation"> </a>

传递给 **GetSpecialLocation** 方法时，指定要获取的特殊位置路径。 
  
|**成员**|**值**|**说明**|
|:-----|:-----|:-----|
|**slBackupFolder** <br/> |0  <br/> |获取"备份文件夹"文件夹位置的路径。  <br/> |
|**slUnfiledNotesSection** <br/> |1  <br/> |获取未筛选的便笺文件夹位置的路径。  <br/> |
|**slDefaultNotebookFolder** <br/> |2  <br/> |获取默认笔记本文件夹位置的路径。  <br/> |
   
## <a name="treecollapsedstatetype"></a>TreeCollapsedStateType
<a name="odc_SpecialLocation"> </a>

当传递给 **QFD** 对象的 **TreeCollapsedState** 方法时，指定是展开还是折叠层次结构树。 
  
|**成员**|**值**|**说明**|
|:-----|:-----|:-----|
|**tcsExpanded** <br/> |0  <br/> |设置要展开的层次结构树。  <br/> |
|**tcsCollapsed** <br/> |1  <br/> |将层次结构树设置为折叠。  <br/> |
   
## <a name="xmlschema-updated-for-onenote-2013"></a>XMLSchema (2013 OneNote更新) 
<a name="odc_SpecialLocation"> </a>

当传递给下列方法之一时，指定OneNote XML 架构的版本：
  
- **OneNote15.Application.GetPageContent**
    
- **OneNote15.Application.FindMeta**
    
- **OneNote15.Application.FindPages**
    
- **OneNote15.Application.GetHierarchy**
    
- **OneNote15.Application.GetPageContent**
    
- **OneNote15.Application.UpdateHierarchy**
    
- **OneNote15.Application.UpdatePageContent**
    
|**成员**|**值**|**说明**|
|:-----|:-----|:-----|
|**xs2007** <br/> |0  <br/> |引用 OneNote 2007 架构。  <br/> |
|**xs2010** <br/> |1  <br/> |引用 OneNote 2010 架构。  <br/> |
|**xs2013** <br/> |2  <br/> |引用 OneNote 2013 架构。  <br/> |
|**xsCurrent** <br/> |2  <br/> |引用当前版本OneNote架构。  <br/> <br/>**注意**：在大多数情况下，我们不建议使用 **xsCurrent，** 因为它可能会导致将来版本的 OneNote。 请改为指定应用构建以处理的架构版本，如 xs2013。           |
   
## <a name="see-also"></a>另请参阅

- [OneNote 开发人员参考](onenote-developer-reference.md)

