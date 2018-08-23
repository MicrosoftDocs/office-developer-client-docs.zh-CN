---
title: IMessageOpenAttach
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMessage.OpenAttach
api_type:
- COM
ms.assetid: b680f5a7-0df3-4e7b-bf3b-f149eb42be8d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 48df5362106e849f061b0797736fad82fafa6584
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22588711"
---
# <a name="imessageopenattach"></a>IMessage::OpenAttach

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
打开附件。 
  
```cpp
HRESULT OpenAttach(
  ULONG ulAttachmentNum,
  LPCIID lpInterface,
  ULONG ulFlags,
  LPATTACH FAR * lppAttach
);
```

## <a name="parameters"></a>参数

 _ulAttachmentNum_
  
> [in]若要打开，存储在附件的**PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) 属性中的附件的索引号。 此索引号唯一地标识邮件中的附件，仅在邮件的上下文中有效。
    
 _lpInterface_
  
> [in]表示要用于访问该附件的接口的界面标识符 (IID) 的指针。 传递 NULL 将导致附件的标准界面或**IAttach**，返回。 
    
 _ulFlags_
  
> [in]位掩码的标志，控制如何打开附件。 可以设置以下标志： 
    
MAPI_BEST_ACCESS 
  
> 请求具有最大网络权限允许用户和最大客户端应用程序访问打开的附件。 例如，如果客户端具有读/写权限，附件应打开具有读/写权限;如果客户端具有只读访问权限，则应具有只读访问权限打开附件。 
    
MAPI_DEFERRED_ERRORS 
  
> 允许**OpenAttach**返回成功，可能之前附件是完全可调用客户端。 如果附件不可用，请进行后续呼叫到它会导致出错。 
    
MAPI_MODIFY 
  
> 请求读/写权限。 默认情况下，具有只读访问权限打开的附件和客户端不应以为，读/写权限授予起作用。 
    
 _lppAttach_
  
> [输出]为打开的附件指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功打开附件。
    
## <a name="remarks"></a>注解

**IMessage::OpenAttach**方法打开邮件附件。 
  
## <a name="notes-to-callers"></a>给调用方的说明

若要打开附件，您必须对附件编号或**PR_ATTACH_NUM**属性的访问。 调用[IMessage::GetAttachmentTable](imessage-getattachmenttable.md)检索邮件的附件表并定位到值，该值代表打开的附件的行。 有关详细信息，请参阅[打开附件](opening-an-attachment.md)。 
  
不要尝试打开一个附件多次;则结果为未定义和依赖于在消息存储提供程序。
  
您可以请求的读/写模式，而不是默认只读模式中打开附件。 但是，是否附件实际上都将在读/写模式中打开是最多的消息存储提供程序。 您可以修改附件，或者是尝试准备处理可能失败，或检查的检索附件的**PR_ACCESS_LEVEL** ([PidTagAccessLevel](pidtagaccesslevel-canonical-property.md)) 属性，如果可用授予的访问级别。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|用于 AttachmentsDlg.cpp  <br/> |CAttachmentsDlg::OpenItemProp  <br/> |MFCMAPI 使用**IMessage::OpenAttach**方法打开 attachment 对象  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMessage : IMAPIProp](imessageimapiprop.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

