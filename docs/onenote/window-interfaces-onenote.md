---
title: 窗口接口 （OneNote 2013)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: e6900ad7-c147-4816-93a9-5773170b115a
description: Window和Windows接口是OneNote 2013 API 对象，使用户能够使用 OneNote 窗口。这些对象允许用户通过 OneNote windows 套枚举并修改某些窗口属性。
ms.openlocfilehash: efc34312def588ecff54c63b3db84f8bf909352b
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25399947"
---
# <a name="window-interfaces-onenote"></a>窗口接口 （OneNote 2013)

**Window**和 **Windows**接口是OneNote 2013 API 对象，使用户能够使用 OneNote 窗口。这些对象允许用户通过 OneNote windows 套枚举并修改某些窗口属性。 
  
## <a name="onenote-window-views"></a>OneNote 窗口视图

以下列表显示了可用于 OneNote 窗口的四个视图模式： 
  
- 普通视图  显示默认 OneNote 窗口中的笔记本和页上的导航窗格都可见。
    
- 完整页面视图  显示查看其不显示笔记本和页窗格中的最小用户界面 (UI)。
    
- 简明  显示一个小窗口，使用户能够短添加注释。您通常会通过 Windows 通知区域中的 OneNote 图标来访问简要说明，但您还可以通过在 OneNote 中的 **视图**选项卡访问它们。 
    
- 停靠到桌面  任何桌面 （类似于任务栏） 的一侧显示可停靠的 OneNote 窗口。此视图可以减少桌面以适应窗口的大小。您可以将只有一个窗口停靠在任何时候，且窗口始终可见不阻止桌面。 
    
下图显示哪些整页视图，停靠至桌面的视图，并在您的桌面上类似于简要说明。
  
**OneNote 视图**

![OneNote 窗口视图](media/ON15Con_views.jpg "OneNote 窗口视图")
  
## <a name="interfaces"></a>接口

本节列出的接口和成员的可用于以编程方式修改 OneNote 窗口。
  
### <a name="windows-interface"></a>Windows 接口

**Windows**界面允许用户访问的打开的 OneNote 窗口集。它是通过 **Application.Windows**访问的 OneNote **Application**类的属性。这将返回枚举的组的 OneNote 窗口。 
  
**属性**

|**名称**|**类型**|**说明**|
|:-----|:-----|:-----|
|**Count** <br/> |ulong  <br/> |获取 **Windows**集中 **Window**对象的数目。  <br/> |
|**CurrentWindow** <br/> |**Window** <br/> |获取活动的 OneNote 窗口的 **Window**对象。  <br/> |
|**Items** <br/> |**Window** <br/> |返回为传入的索引值相对应的 **Window**对象。此属性不能直接访问。若要返回 **Window**对象，请使用 **Windows [(uint) index]**。 <br/> |
   
### <a name="window-interface"></a>窗口界面

**Window**界面允许用户访问的每个窗口的某些属性。可以通过枚举通过 **Application**类的 **Windows**属性来访问每个 OneNote 窗口。 
  
**属性**

|**名称**|**类型**|**说明**|
|:-----|:-----|:-----|
|**Active** <br/> |bool  <br/> |获取或设置一个值，指示窗口是否是活动的 OneNote 窗口。  <br/> |
|**Application** <br/> |**Application** <br/> |获取与窗口关联的 OneNote **Application**对象。  <br/> |
|**CurrentPageId** <br/> |string  <br/> |获取窗口的活动的 OneNote 页面的对象 ID。  <br/> |
|**CurrentSectionId** <br/> |string  <br/> |获取窗口的活动 OneNote 部分的对象 ID。  <br/> |
|**CurrentSectionGroupId** <br/> |string  <br/> |获取窗口的活动的 OneNote 分区组的对象 ID。  <br/> |
|**CurrentNotebookId** <br/> |string  <br/> |获取窗口的活动的 OneNote 笔记本的对象 ID。  <br/> |
|**DockedLocation** <br/> |**DockedLocation** <br/> |获取或设置 OneNote 窗口的停靠的位置。  <br/> |
|**FullPageView** <br/> |bool  <br/> |获取或设置一个值，指示窗口是否是在整页视图 （最少 UI 视图）。  <br/> |
|**SideNote** <br/> |bool  <br/> |获取或设置一个值，指示窗口是否是一个简明窗口。  <br/> |
|**WindowHandle** <br/> |ulong  <br/> |获取 OneNote 窗口的句柄 ID。  <br/> |
   
**方法**
  
可以使用 **Window**接口的以下方法导航到 OneNote 窗口中的指定对象或指定的 Url。 
  
**NavigateTo**

|||
|:-----|:-----|
|**描述** <br/> |导航到 OneNote 窗口中指定的对象。例如，您可以导航到节、 页面和页中的大纲元素。  <br/> |
|**语法** <br/> | `HRESULT NavigateTo(`           ` [in]BSTR bstrHierarchyObjectID, `           ` [in]BSTR bstrObjectID); ` <br/> |
|**参数** <br/> | _bstrHierarchyObjectID_ 层次结构 OneNote 您想要导航到的对象 ID。OneNote 笔记本、 节、 节组或页上，可以引用的对象 ID。 <br/>  _bstrObjectID_ 的 OneNote ID 的特定对象以导航到 OneNote 页面中。如果用户不希望以导航到页面上的特定对象，此参数设置为 null。 <br/> |
   
**NavigateToUrl**

|||
|:-----|:-----|
|**描述** <br/> |如果传递的 OneNote 链接 （onenote: / /)，在 OneNote 中打开 OneNote 窗口到相应位置。 但是，如果链接是外部链接，如 https:// 或 file://，将出现一个安全对话框。 时开除，OneNote 尝试打开链接，并返回 HResult.hrObjectDoesNotExist 错误。  <br/> |
|**语法** <br/> | `HRESULT NavigateToUrl (`           ` [in]BSTR bstrUrl); ` <br/> |
|**参数** <br/> | _bstrUrl_ 要导航到的 URL。  <br/> |
   
**SetDockedLocation**

|||
|:-----|:-----|
|**描述** <br/> |停靠窗口指定 **dockLocation**和在 **ptMonitor**监视器的位置。  <br/> |
|**语法** <br/> | `HRESULT SetDockedLocation`(           `[in] DockLocation dockLocation,`           `[in] POINT ptMonitor);` <br/> |
|**参数** <br/> | _dockLocation_ -指示OneNote 2013窗口的停靠的位置。  <br/>  _ptMonitor_ -在 x，其中监视窗口 y 坐标 （可选） 指示应固定。  <br/> |
   
## <a name="example"></a>示例

下面的代码将循环访问 OneNote 窗口，以查找停靠的窗口中。如果没有停靠的窗口存在，该示例将停靠活动窗口。如果没有活动窗口存在，该代码将创建一个新的停靠的窗口。
  
```cs
using System;
using System.Diagnostics;
using Microsoft.Office.Interop.OneNote;
namespace SampleWND
{
    class DockOneNoteWindow
    {
        static void Main(string[] args)
        {
            Microsoft.Office.Interop.OneNote.Application app = new Microsoft.Office.Interop.OneNote.Application();
            // Search through all OneNote windows for a docked window and activate it.
            bool foundDockedWND = false;
            for (int i = 0; i < app.Windows.Count; i++)
            {
                if (app.Windows[(uint) i].DockedLocation != DockLocation.dlNone)
                {
                    foundDockedWND = true;
                    app.Windows[(uint) i].Active = true;
                }
            }
            
            // If no docked window exists, dock the active window.
            if (!foundDockedWND && (app.Windows.Count > 0))
                app.Windows.CurrentWindow.DockedLocation = DockLocation.dlDefault;
            // If no active window exists, create a new docked window.
            if (app.Windows.Count < 1)
            {
                Process oneProc = new Process();
                oneProc.StartInfo.FileName = "onenote.exe";
                oneProc.StartInfo.Arguments = "/docked";
                oneProc.Start();
            }
        }
    }
}

```

## <a name="see-also"></a>另请参阅

- [OneNote 开发人员参考](onenote-developer-reference.md)

