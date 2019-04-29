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
  
打开一个附件。 
  
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
  
> 实时要打开的附件的索引号 (存储在附件的**PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) 属性中)。 此索引号唯一标识邮件中的附件, 并且仅在邮件的上下文中有效。
    
 _lpInterface_
  
> 实时指向接口标识符 (IID) 的指针, 该接口标识符表示要用于访问附件的接口。 在返回的附件的标准接口或**IAttach**中传递 NULL 结果。 
    
 _ulFlags_
  
> 实时控制附件打开方式的标志的位掩码。 可以设置以下标志: 
    
MAPI_BEST_ACCESS 
  
> 请求使用用户允许的最大网络权限和最大客户端应用程序访问权限打开附件。 例如, 如果客户端具有读/写权限, 则应以读/写权限打开附件;如果客户端具有只读访问权限, 则应以只读访问权限打开附件。 
    
MAPI_DEFERRED_ERRORS 
  
> 允许**OpenAttach**成功返回, 这可能是在将附件完全提供给呼叫客户端之前。 如果附件不可用, 则对其进行后续调用可能会导致出错。 
    
MAPI_MODIFY 
  
> 请求读取/写入权限。 默认情况下, 将使用只读访问权限打开附件, 并且客户端不应在假定已授予读/写权限时才起作用。 
    
 _lppAttach_
  
> 排除指向打开的附件的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功打开附件。
    
## <a name="remarks"></a>说明

**IMessage:: OpenAttach**方法打开邮件的附件。 
  
## <a name="notes-to-callers"></a>给调用方的说明

若要打开附件, 您必须具有对其附件编号或**PR_ATTACH_NUM**属性的访问权限。 调用[IMessage:: GetAttachmentTable](imessage-getattachmenttable.md)以检索邮件的附件表, 并找到代表要打开的附件的行。 有关详细信息, 请参阅[打开附件](opening-an-attachment.md)。 
  
不要尝试多次打开一个附件;结果未定义, 并依赖于邮件存储区提供程序。
  
您可以请求以读/写模式打开附件, 而不是以默认的只读模式打开。 但是, 是否实际以读/写模式打开附件将由邮件存储提供程序提供。 您可以尝试修改附件、准备处理可能的故障, 或者检查通过检索附件的**PR_ACCESS_LEVEL** ([PidTagAccessLevel](pidtagaccesslevel-canonical-property.md)) 属性 (如果可用) 而获得的访问级别。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|AttachmentsDlg 用于  <br/> |CAttachmentsDlg:: OpenItemProp  <br/> |MFCMAPI 使用**IMessage:: OpenAttach**方法打开附件对象,  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMessage : IMAPIProp](imessageimapiprop.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

