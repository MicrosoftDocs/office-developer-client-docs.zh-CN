---
title: IConverterSession IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IConverterSession
api_type:
- COM
ms.assetid: 24f7a14a-aa6f-4045-054b-4a7aefef25e4
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2db55d6318cf02dd131d07b34841922e61605147
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432315"
---
# <a name="iconvertersession--iunknown"></a>IConverterSession : IUnknown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
允许在 MIME 对象和 MAPI 邮件之间进行转换。 这在通过 Internet 传输邮件时可能很有用。
  
|||
|:-----|:-----|
|提供者：  <br/> |CLSID_IConverterSession  <br/> |
|接口标识符:  <br/> |IID_IConverterSession  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|**[SetAdrBook](iconvertersession-setadrbook.md)** <br/> |指定 mapi 到 mime 转换器在将 MAPI 邮件转换为 MIME 流时用于解析不明确地址的可选 MAPI 通讯簿。  <br/> |
|**[SetEncoding](iconvertersession-setencoding.md)** <br/> |初始化要在转换过程中使用的编码。  <br/> |
| *占位符成员*  <br/> | *不支持或记录。*  <br/> |
|**[MIMEToMAPI](iconvertersession-mimetomapi.md)** <br/> |将 MIME 流转换为 MAPI 邮件。  <br/> |
|**[MAPIToMIMEStm](iconvertersession-mapitomimestm.md)** <br/> |将 MAPI 邮件转换为 MIME 流。  <br/> |
| *占位符成员*  <br/> | *不支持或记录。*  <br/> |
| *占位符成员*  <br/> | *不支持或记录。*  <br/> |
| *占位符成员*  <br/> | *不支持或记录。*  <br/> |
|**[SetTextWrapping](iconvertersession-settextwrapping.md)** <br/> |设置转换器在**MAPIToMIMEStm**中返回的 MIME 流的文本换行宽度。  <br/> |
|**[SetSaveFormat](iconvertersession-setsaveformat.md)** <br/> |设置转换器在**MAPIToMIMEStm**中返回 MIME 流的格式。  <br/> |
| *占位符成员*  <br/> | *不支持或记录。*  <br/> |
|**[SetCharSet](iconvertersession-setcharset.md)** <br/> |指定 mapi 到 mime 转换器在将 mapi 邮件转换为 mime 流时使用的可选字符集。  <br/> |
   
## <a name="remarks"></a>说明

在使用**MAPIToMIMEStm**执行转换之前调用**SetEncoding** 。 
  
## <a name="see-also"></a>另请参阅



[关于 MAPI-MIME 转换 API](about-the-mapi-mime-conversion-api.md)
  
[MAPI 常量](mapi-constants.md)

