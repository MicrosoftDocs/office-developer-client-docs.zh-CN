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
ms.openlocfilehash: e0c3747b48526b715f976e7bf3c142097c85f29a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405896"
---
# <a name="imessageopenattach"></a>IMessage::OpenAttach

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
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
  
> [in]要打开的附件的索引号，存储在附件的 PR_ATTACH_NUM ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) 属性中。  此索引号唯一标识邮件中的附件，并且仅在邮件上下文中有效。
    
 _lpInterface_
  
> [in]指向接口标识符 (IID) 表示用于访问附件的接口的指针。 传递 NULL 会导致返回附件的标准接口 **IAttach。** 
    
 _ulFlags_
  
> [in]控制附件打开方式的标志的位掩码。 可以设置以下标志： 
    
MAPI_BEST_ACCESS 
  
> 请求以用户允许的最大网络权限和最大客户端应用程序访问权限打开附件。 例如，如果客户端具有读/写权限，则应该使用读/写权限打开附件;如果客户端具有只读访问权限，则应该以只读访问权限打开附件。 
    
MAPI_DEFERRED_ERRORS 
  
> 允许 **OpenAttach** 在附件完全可供调用客户端使用之前成功返回。 如果附件不可用，则对附件进行后续调用会导致错误。 
    
MAPI_MODIFY 
  
> 请求读/写权限。 默认情况下，使用只读访问权限打开附件，客户端不应在已授予读/写权限的假设下工作。 
    
 _lppAttach_
  
> [out]指向打开的附件的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功打开附件。
    
## <a name="remarks"></a>备注

**IMessage：：OpenAttach** 方法打开邮件的附件。 
  
## <a name="notes-to-callers"></a>给调用方的说明

若要打开附件，您必须有权访问其附件 **编号或PR_ATTACH_NUM** 属性。 调用 [IMessage：：GetAttachmentTable](imessage-getattachmenttable.md) 以检索邮件的附件表并找到表示要打开的附件的行。 有关详细信息 [，请参阅打开](opening-an-attachment.md) 附件。 
  
不要尝试多次打开一个附件;结果未定义，取决于邮件存储提供程序。
  
您可以请求以读/写模式而不是默认的只读模式打开附件。 但是，是否实际以读/写模式打开附件取决于邮件存储提供程序。 您可以尝试修改附件、准备处理可能失败，或者检查通过检索附件的 **PR_ACCESS_LEVEL** ([PidTagAccessLevel](pidtagaccesslevel-canonical-property.md)) 属性（如果可用）授予的访问权限级别。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|AttachmentsDlg.cpp 用于  <br/> |CAttachmentsDlg：：OpenItemProp  <br/> |MFCMAPI 使用 **IMessage：：OpenAttach** 方法打开附件对象，  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMessage : IMAPIProp](imessageimapiprop.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

