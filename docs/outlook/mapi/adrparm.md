---
title: ADRPARM
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- ADRPARM
api_type:
- COM
ms.assetid: 35cd57b4-9901-456c-bf06-1f84e274eb4e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9663a25a50d914f47cff48124898d16318bbbc43
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425895"
---
# <a name="adrparm"></a>ADRPARM

**适用于**：Outlook 2013 | Outlook 2016 
  
描述常用地址对话框的显示和行为。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
   
```cpp
typedef struct _ADRPARM
{
  ULONG cbABContEntryID;
  LPENTRYID lpABContEntryID;
  ULONG ulFlags;
  LPVOID lpReserved;
  ULONG ulHelpContext;
  LPSTR lpszHelpFileName;
  LPFNABSDI lpfnABSDI;
  LPFNDISMISS lpfnDismiss;
  LPVOID lpvDismissContext;
  LPSTR lpszCaption;
  LPSTR lpszNewEntryTitle;
  LPSTR lpszDestWellsTitle;
  ULONG cDestFields;
  ULONG nDestFieldFocus;
  LPSTR FAR *lppszDestTitles;
  ULONG FAR *lpulDestComps;
  LPSRestriction lpContRestriction;
  LPSRestriction lpHierRestriction;
} ADRPARM, FAR *LPADRPARM;

```

## <a name="members"></a>Members

**cbABContEntryID**
  
> **lpABContEntryID** 指向的条目标识符中的字节数。
    
**lpABContEntryID**
  
> 指向容器的条目标识符的指针，该容器提供地址对话框中显示的初始收件人地址列表。
    
**ulFlags**
  
> 与各种地址对话框选项相关联的标志的位掩码。 可以设置以下标志：
    
AB_RESOLVE
  
> 允许在关闭地址对话框后解析所有名称。 如果名称解析过程中出现不明确的条目，则会出现一个对话框，提示用户进行解析。 设置此标志可保证 [IAddrBook：：Address](iaddrbook-address.md) 返回的所有名称已解析。 
    
AB_SELECTONLY
  
> 禁用为收件人列表创建一次地址。 此标志仅在对话框是模式对话框时使用，如要设置的 DIALOG_MODAL标记所指示。
    
ADDRESS_ONE
  
> 用户可以仅从列表中选择一个收件人，而不是从列表中选择多个收件人。 此标志仅在 **cDestFields** 为零且对话框为模式时有效，如要设置的 DIALOG_MODAL标记所指示。 
    
DIALOG_MODAL
  
> 导致显示常用地址对话框的模式版本。 应设置此DIALOG_SDI或值;它们不能同时设置。 
    
DIALOG_OPTIONS
  
> 使 **"发送选项** "按钮显示在对话框中。 此标志仅在对话框是模式对话框时使用，如要设置的 DIALOG_MODAL标记所指示。 
    
DIALOG_SDI
  
> 导致显示公用地址对话框的无模式版本。 应设置此DIALOG_MODAL或值;它们不能同时设置。 对于DIALOG_SDI客户端，将忽略 Outlook 标志，并显示对话框的模式版本。 因此 [，IAddrBook：：Address](iaddrbook-address.md)的 _lpulUIParam_ 参数不应期望指向句柄的指针。
    
**lpReserved**
  
> 保留，必须为零。
    
**ulHelpContext**
  
> 指定当用户单击地址对话框中的"帮助"按钮时将首先显示的"帮助"中的上下文。 
    
**lpszHelpFileName**
  
> 指向将与地址对话框关联的帮助文件的名称的指针。 **lpszHelpFileName** 成员与 **ulHelpContext** 一起用于调用 Windows **WinHelp** 函数。 
    
**lpfnABSDI**
  
> 指向基于 [ACCELERATEABSDI](accelerateabsdi.md) 原型或 NULL 的 MAPI 函数的指针。 此成员仅适用于对话框的无模式版本，如要设置的 DIALOG_SDI 标志所指示。 生成要传递到 [IAddrBook：：Address](iaddrbook-address.md) **的 ADRPARM** 结构的客户端必须始终将 **lpfnABSDI** 成员设置为 NULL。 如果设置了DIALOG_SDI，MAPI 会先将它设置为有效的函数，然后再返回。 客户端在邮件循环中调用此函数，以确保通讯簿对话框中的加速键正常工作。 当对话框关闭并且 MAPI 调用 **lpfnDismiss** 成员指向的函数时，客户端应从消息循环中取消 **HOOKABSDI** 函数。 
    
**lpfnDismiss**
  
> 指向基于 [DISMISSMODELESS](dismissmodeless.md) 原型或 NULL 的函数的指针。 此成员仅适用于对话框的无模式版本，如要设置的 DIALOG_SDI 指示。 当用户关闭无模式地址对话框时，MAPI 将调用 **DISMISSMODELESS** 函数，并通知调用 **IAddrBook：：Address** 的客户端对话框不再处于活动状态。 
    
**lpvDismissContext**
  
> 指向要传递给 **lpfnDismiss** 成员指向 **的 DISMISSMODELESS** 函数的上下文信息的指针。 此成员仅适用于对话框的无模式版本，如要设置的 DIALOG_SDI 指示。 
    
**lpszCaption**
  
> 指向要用作常用地址对话框标题的文本的指针。
    
**lpszNewEntryTitle**
  
> 指向要用作调用"新建项"对话框或其他对话框的按钮的按钮标签的文本的指针。 
    
**lpszDestWellsTitle**
  
> 指向要用作收件人文本框控件标题的文本的指针，这些控件可以显示在常用地址对话框的模式版本中。 此成员不用于无模式对话框。 
    
**cDestFields**
  
> 地址对话框模式版本中收件人文本框控件的计数;如果对话框为无模式，则为零。 只有在满足以下条件时，才能打开"地址"对话框进行浏览： 
    
  - **cDestFields** 成员设置为零。 
    
  - 设置DIALOG_BOX标记。
    
  - 未ADDRESS_ONE标志。
    
  将 **cDestFields** 0XFFFFFFFF表示 MAPI 应创建默认数量的收件人文本框控件。 在这种情况下 **，lppszDestTitles** 和 **lpulDestComps** 成员必须为 NULL。 
    
**nDestFieldFocus**
  
> 指示在对话框的模式版本出现时应具有初始焦点的特定文本框控件。 此值必须介于 0 和 **cDestFields** 的值减 1 之间。 
    
**lppszDestTitles**
  
> 指向与在地址对话框的模式版本中显示的每个文本框控件关联的按钮的标签数组的指针。 **cDestFields** 成员的值指示数组中包含的标签数。 如果 **lppszDestTitles** 成员为 NULL， **则 Address** 方法使用默认标题。 
    
**lpulDestComps**
  
> 指向与每个文本框控件关联的收件人类型值（如 MAPI_TO、MAPI_CC 和 MAPI_BCC）的数组的指针。 **CDestFields** 成员的值指示数组中包含的收件人类型数。 **lpulDestComps** 指向的值可用于将每个收件人的 PR_RECIPIENT_TYPE  ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md)) 属性。 如果 **lpulDestComps** 成员为 NULL， **则 Address** 方法使用默认收件人类型。 
    
**lpContRestriction**
  
> 指向限制可在对话框中显示的地址条目类型的 [SRestriction](srestriction.md) 结构的指针。 
    
**lpHierRestriction**
  
> 指向 **SRestriction** 结构的指针，该结构限制提供要显示在对话框中的地址条目的通讯簿容器。 
    
## <a name="remarks"></a>备注

**客户端和服务提供商使用 ADRPARM** 结构来控制 MAPI 公用地址对话框的外观和行为。 地址对话框有两种：无模式和模式。 **ADRPARM** 结构中的一些成员适用于两个版本的对话框，但有些仅适用于这两个版本之一。 下表将 **ADRPARM** 结构的成员与常用地址对话框的使用关联。 
  
|ADRPARM 成员|对话框的类型|
|:-----|:-----|
|**cbABContEntryID** 和 **lpABContEntryID** <br/> |模式和无模式  <br/> |
|**ulFlags** <br/> |模式和无模式  <br/> |
|**lpReserved** <br/> |模式和无模式  <br/> |
|**ulHelpContext** 和 **lpszHelpFileName** <br/> |模式和无模式  <br/> |
|**lpfnABSDI** <br/> |Modeless  <br/> |
|**lpfnDismiss** 和 **lpvDismissContext** <br/> |Modeless  <br/> |
|**lpszCaption** <br/> |模式和无模式  <br/> |
|**lpszNewEntryTitle** <br/> |Modal  <br/> |
|lpszDestWellsTitle、cDestFields、nDestFieldFocus、lppszDestTitles 和 **lpulDestComps**     <br/> |Modal  <br/> |
|**lpContRestriction** <br/> |模式和无模式  <br/> |
|**lpHierRestriction** <br/> |模式和无模式  <br/> |
   
无模式对话框是一个或多个通讯簿容器中的条目的只读显示。 该对话框可以显示所选容器的所有条目，或限制为仅与由限制建立的条件匹配的那些条目和容器。 **lpContRestriction** 指向的内容限制可以限制显示的条目类型 **，lpHierRestriction** 指向的层次结构限制可以限制提供条目的容器。 为了在对话框关闭时通知调用方，MAPI 调用由调用方提供的与 [DISMISSMODELESS](dismissmodeless.md) 原型匹配的函数。 另一个与[ACCELERATEABSDI](accelerateabsdi.md)原型匹配的函数由 MAPI 提供，由 Windows 消息循环中的调用方调用，以便于键盘快捷方式的运行。 当客户端调用 [IAddrBook：：Address](iaddrbook-address.md) 或服务提供商调用 [IMAPISupport：：Address](imapisupport-address.md)时，可以显示无模式版本的 MAPI 地址对话框。 
  
模式对话框是一个或多个容器中的条目的读/写显示。 其内容可能会像无模式版本一样受到 **lpContRestriction** 和 **lpHierRestriction** 成员中设置的限制的影响。 除了显示容器项的列表框之外，模式对话框还可以包含一到三个文本框控件，用于保持用户选择的条目。 每个编辑控件都与特定的收件人类型或 **PR_RECIPIENT_TYPE属性（** 如MAPI_TO）。 模式地址对话框可以通过任一 **Address** 方法显示，或在客户端调用 [IAddrBook：:D etails](iaddrbook-details.md) 和服务提供商调用 [IMAPISupport：:D etails 时显示](imapisupport-details.md)。 
  
此图包含两个文本框控件，因为控制此对话框显示的 **ADRPARM** 结构的 **cDestFields** 成员设置为 2。 第一个控件具有初始焦点， **因为 nDestFieldFocus** 成员设置为 0。 
  
**lpszNewEntryTitle** 成员指向按钮标签的文本，当选中该标签时，该成员会导致显示其他对话框。 通常，如模式对话框的图示所示，该按钮标记为"新建"，并且出现的对话框列出了配置文件中任何通讯簿提供程序都可以创建的所有地址类型。 客户端 **通过调用**[IAddrBook：：NewEntry，](iaddrbook-newentry.md)为 _cbEidNewEntryTpl_ 参数传递零，在用户选择按钮时为 _lpEidNewEntryTpl_ 参数传递 NULL 来显示此"新建条目"对话框。 此对话框中包含的信息来自 MAPI 一对一表。 
  
此对话框中的每一项都与模板相关联，模板用于输入创建特定类型地址所需的数据。 大多数通讯簿提供程序都为可以创建的每种地址条目类型提供一个模板。 当用户从此对话框中进行选择时，MAPI 将显示相应的模板。
  
**ADRPARM** 结构的 **ulFlags** 成员最重要的四位包含标识 **ADRPARM** 结构的版本的版本号。 当前版本为 0 (零) 或 ADRPARM_HELP_CTX。 MAPI 的当前实现对于除零外的任何版本的结构都将失败。 
  
结构的未来版本可能完全不同;它们可能不支持零版本结构。 提供了以下宏，用于从 **ulFlags** 成员中提取版本号以及将版本号与定义标志合并： 
  
- **GET_ADRPARM_VERSION (** _ulFlags)_ 
- **SET_ADRPARM_VERSION (** _ulFlags_， _ ulVersion _)  
- **ADRPARM_HELP_CTX**
  
## <a name="see-also"></a>另请参阅

- [ACCELERATEABSDI](accelerateabsdi.md)
- [DISMISSMODELESS](dismissmodeless.md)
- [IAddrBook::Address](iaddrbook-address.md)
- [IMAPISupport::Address](imapisupport-address.md)
- [SRestriction](srestriction.md)
- [MAPI 结构](mapi-structures.md)

