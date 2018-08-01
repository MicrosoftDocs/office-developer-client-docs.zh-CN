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
ms.openlocfilehash: ad26cb9b77404d6470f7a8d787eb85edc5cce402
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/21/2018
ms.locfileid: "19774536"
---
# <a name="adrparm"></a>ADRPARM

**适用于**： Outlook 
  
介绍的显示和行为的通用的地址对话框。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
   
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
  
> 由**lpABContEntryID**指向中的项标识符的字节数。
    
**lpABContEntryID**
  
> 提供在地址对话框中显示的收件人地址的初始列表容器的项标识符的指针。
    
**ulFlags**
  
> 与各种地址对话框选项相关联标志的位掩码。 可以设置以下标志：
    
AB_RESOLVE
  
> 启用所有名称解析后关闭地址对话框。 如果有模糊名称解析过程从结果的条目，将出现一个对话框提示用户输入中解决它们的帮助。 此标志保证所有[IAddrBook::Address](iaddrbook-address.md)返回的名称解析的设置。 
    
AB_SELECTONLY
  
> 禁用一次性地址的收件人列表的创建。 标志所指示的 DIALOG_MODAL 设置是一个模式对话框，对话框的情况下，才使用此标志。
    
ADDRESS_ONE
  
> 用户可以从列表中选择一个收件人，而不是多个收件人。 仅当**cDestFields**为零，并且对话框是一个模式对话框，如标志所指示的 DIALOG_MODAL 设置时，此标志是有效。 
    
DIALOG_MODAL
  
> 使通用地址对话框要显示的模式版本。 此标志或 DIALOG_SDI 应该设置;他们不能同时设置。 
    
DIALOG_OPTIONS
  
> 使**发送选项**按钮，在对话框中显示。 标志所指示的 DIALOG_MODAL 设置是一个模式对话框，对话框的情况下，才使用此标志。 
    
DIALOG_SDI
  
> 使通用地址对话框要显示的无模式版本。 此标志或 DIALOG_MODAL 应该设置;他们不能同时设置。 DIALOG_SDI 标志，则忽略非 Outlook 客户端，并将显示模式对话框中的版本。 因此，不应[IAddrBook::Address](iaddrbook-address.md)的_lpulUIParam_参数中预期的句柄的指针。
    
**lpReserved**
  
> 保留，必须为零。
    
**ulHelpContext**
  
> 指定的上下文中**帮助**的将首先显示当用户单击地址对话框中的帮助按钮。 
    
**lpszHelpFileName**
  
> 指针，指向地址对话框与关联的帮助文件的名称。 **LpszHelpFileName**成员一起**ulHelpContext**调用 Windows **WinHelp**函数。 
    
**lpfnABSDI**
  
> 指向 MAPI 函数基于[ACCELERATEABSDI](accelerateabsdi.md)原型或 NULL。 此成员适用于无模式对话框中，版如标志所指示的 DIALOG_SDI 设置。 构建要传递给[IAddrBook::Address](iaddrbook-address.md) **ADRPARM**结构的客户端必须始终设置为 NULL 的**lpfnABSDI**成员。 如果设置了 DIALOG_SDI 标志，MAPI 将然后将其设置为有效的函数返回之前。 客户端调用该函数从其邮件循环，以确保地址中的加速键书籍对话框框工作。 当被关闭对话框并 MAPI 调用指向**lpfnDismiss**成员的函数时，客户端应断开**ACCELERATEABSDI**函数从其消息循环。 
    
**lpfnDismiss**
  
> 指向函数基于[DISMISSMODELESS](dismissmodeless.md)原型或 NULL。 此成员仅适用于无模式版本的对话框中，如标志所指示的 DIALOG_SDI 设置。 MAPI 调用的**DISMISSMODELESS**函数时在用户关闭无模式的地址对话框，通知调用**IAddrBook::Address**对话框中不再处于活动状态的客户端。 
    
**lpvDismissContext**
  
> 指向上下文信息传递给**DISMISSMODELESS**函数指针指向由**lpfnDismiss**成员。 此成员仅适用于无模式版本的对话框中，如标志所指示的 DIALOG_SDI 设置。 
    
**lpszCaption**
  
> 指向要用作通用的地址对话框标题文本。
    
**lpszNewEntryTitle**
  
> 指向要用作调用**新项**对话框或另一个对话框中按钮的按钮标签的文本。 
    
**lpszDestWellsTitle**
  
> 指向要用作收件人文本框控件可以显示模式版本的通用的地址对话框中的标题文本。 此成员不用于无模式对话框。 
    
**cDestFields**
  
> 在地址对话框中或零，如果无模式对话框模式版本收件人文本框控件的计数。 地址对话框中处于打开状态以浏览仅当满足以下条件： 
    
  - **CDestFields**成员设置为零。 
    
  - 设置 DIALOG_BOX 标志。
    
  - 未设置 ADDRESS_ONE 标志。
    
  设置为 0XFFFFFFFF **cDestFields**意味着框控件 MAPI 应创建收件人的文本的默认数。 在这种情况下的**lppszDestTitles**和**lpulDestComps**成员必须为 NULL。 
    
**nDestFieldFocus**
  
> 指示特定文本框控件显示的对话框中的模式版本时，应具有的初始焦点。 该值必须介于 0 和**cDestFields**减 1 之间的值之间。 
    
**lppszDestTitles**
  
> 指向与每个文本框控件的显示模式版本中的地址对话框的按钮标签的数组。 **CDestFields**成员的值指示数组中包含的标签的数目。 如果**lppszDestTitles**成员为 NULL，则该**地址**方法将使用默认标题。 
    
**lpulDestComps**
  
> 指向数组的收件人类型值，如 MAPI_TO、 MAPI_CC 和 MAPI_BCC，这是与每个文本框控件相关联。 **CDestFields**成员的值指示的数组中包含的收件人类型的数目。 用于将每个收件人的**PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md)) 属性设置所指的**lpulDestComps**的值。 如果**lpulDestComps**成员为 NULL，则该**地址**方法将使用默认的收件人类型。 
    
**lpContRestriction**
  
> 指向[SRestriction](srestriction.md)结构限制可在对话框中显示的地址条目的类型。 
    
**lpHierRestriction**
  
> 指向限制可以提供要显示在对话框中的地址条目的地址簿容器**SRestriction**结构。 
    
## <a name="remarks"></a>说明

由客户端和服务提供商使用的**ADRPARM**结构用于控制的外观和行为的 MAPI 通用地址对话框。 有两种类型的地址对话框： 无模式和模式。 一些**ADRPARM**结构中的成员将应用于两个版本的对话框中，但某些仅适用于两个版本之一。 下表在其使用通用的地址对话框中与**ADRPARM**结构的成员。 
  
|ADRPARM 成员|对话框类型|
|:-----|:-----|
|**cbABContEntryID**和**lpABContEntryID** <br/> |模式和无模式  <br/> |
|**ulFlags** <br/> |模式和无模式  <br/> |
|**lpReserved** <br/> |模式和无模式  <br/> |
|**ulHelpContext**和**lpszHelpFileName** <br/> |模式和无模式  <br/> |
|**lpfnABSDI** <br/> |Modeless  <br/> |
|**lpfnDismiss**和**lpvDismissContext** <br/> |Modeless  <br/> |
|**lpszCaption** <br/> |模式和无模式  <br/> |
|**lpszNewEntryTitle** <br/> |Modal  <br/> |
|**lpszDestWellsTitle**、 **cDestFields**、 **nDestFieldFocus**、 **lppszDestTitles**和**lpulDestComps** <br/> |Modal  <br/> |
|**lpContRestriction** <br/> |模式和无模式  <br/> |
|**lpHierRestriction** <br/> |模式和无模式  <br/> |
   
无模式对话框是只读的显示的一个或多个地址簿容器中的条目。 对话框可显示所选的容器中的所有项或被限制为只有那些条目和匹配建立限制条件的容器。 所指的**lpContRestriction**内容限制可以限制的显示条目类型并由**lpHierRestriction**指向的层次结构限制可以限制提供条目的容器。 若要向呼叫者时消除对话框中，MAPI，请调用匹配[DISMISSMODELESS](dismissmodeless.md)原型呼叫者提供的函数。 另一个函数，一个匹配[ACCELERATEABSDI](accelerateabsdi.md)原型，是供稿 MAPI，调用 Windows 邮件循环中呼叫者，为了方便的键盘快捷方式工作。 客户端调用[IAddrBook::Address](iaddrbook-address.md)时或服务提供商调用[IMAPISupport::Address](imapisupport-address.md)时，可以显示 MAPI 地址对话框中的无模式版本。 
  
模式对话框显示的一个或多个容器中的条目的读/写。 其内容会受到影响相同的方式，如成员**lpContRestriction**和**lpHierRestriction**中设置的限制的无模式版本。 显示容器条目的列表中，除了模式对话框可以包含一到三个文本框控件的容纳用户所选的项。 每个编辑控件相关联的特定收件人类型或如 MAPI_TO **PR_RECIPIENT_TYPE**属性。 客户端调用[IAddrBook::Details](iaddrbook-details.md)和服务提供商呼叫[IMAPISupport::Details](imapisupport-details.md)时，可以按的**地址**方法或显示模式的地址对话框。 
  
此图中包括两个文本框控件，因为控制的此对话框中显示的**ADRPARM**结构的**cDestFields**成员设置为 2。 第一个控件具有初始焦点，因为**nDestFieldFocus**成员设置为 0。 
  
**LpszNewEntryTitle**成员指向选中后，将导致附加的对话框中显示的按钮标签的文本。 通常情况下，如下图所示的模式对话框，该按钮标记为**新建**和出现的对话框中列出的所有通讯簿提供程序配置文件中的任一可以创建的地址类型。 客户端导致通过调用[IAddrBook::NewEntry](iaddrbook-newentry.md)和传递零_cbEidNewEntryTpl_参数和_lpEidNewEntryTpl_参数为空，用户选择按钮时显示此**新项**对话框。 在此对话框中包含的信息将来自 MAPI 一次性表。 
  
在此对话框中的每个条目都与输入要创建特定类型的地址所需的数据的模板关联。 大多数通讯簿提供程序提供每种类型的地址条目，他们可以创建一个的模板。 当用户从该对话框中进行选择时，MAPI 显示相应的模板。
  
**ADRPARM**结构的**ulFlags**成员的最重要的四个字节包含标识**ADRPARM**结构的版本的版本号。 当前版本是 0 （零） 或 ADRPARM_HELP_CTX。 当前的 MAPI 实现将失败的任何版本的非零的结构。 
  
结构的未来版本可能完全不同;他们可能不支持的版本零结构。 下面的宏提供从**ulFlags**成员中提取的版本号和将它与定义的标志组合： 
  
- **GET_ADRPARM_VERSION**(_ulFlags_) 
- **SET_ADRPARM_VERSION**(_ulFlags_，_ ulVersion _) 
- **ADRPARM_HELP_CTX**
  
## <a name="see-also"></a>另请参阅

- [ACCELERATEABSDI](accelerateabsdi.md)
- [DISMISSMODELESS](dismissmodeless.md)
- [IAddrBook::Address](iaddrbook-address.md)
- [IMAPISupport::Address](imapisupport-address.md)
- [SRestriction](srestriction.md)
- [MAPI 结构](mapi-structures.md)

