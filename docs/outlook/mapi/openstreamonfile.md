---
title: OpenStreamOnFile
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.OpenStreamOnFile
api_type:
- COM
ms.assetid: 01fa459f-597d-4b16-b340-a79fb270cd71
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b05f5b30eceb7df1bed76c64f4bdda87ede0e463
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348627"
---
# <a name="openstreamonfile"></a>OpenStreamOnFile

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
分配并初始化 OLE **IStream**对象以访问文件的内容。 此函数采用 ANSI 字符串作为文件名, 包括路径和文件扩展名, 因此, 建议使用此函数的 Unicode 版本[OpenStreamOnFileW](openstreamonfilew.md)。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序  <br/> |
   
```cpp
HRESULT STDMETHODCALLTYPE OpenStreamOnFile(
  LPALLOCATEBUFFER lpAllocateBuffer,
  LPFREEBUFFER lpFreeBuffer,
  ULONG ulFlags,
  LPSTR lpszFileName,
  LPSTR lpszPrefix,
  LPSTREAM FAR * lppStream
);
```

## <a name="parameters"></a>参数

 _lpAllocateBuffer_
  
> 实时指向用于分配内存的[MAPIAllocateBuffer](mapiallocatebuffer.md)函数的指针。 
    
 _lpFreeBuffer_
  
> 实时指向用于释放内存的[MAPIFreeBuffer](mapifreebuffer.md)函数的指针。 
    
 _ulFlags_
  
> 实时用于控制要通过 OLE **IStream**对象访问的文件的创建或打开的标志的位掩码。 可以设置以下标志: 
    
SOF_UNIQUEFILENAME 
  
> 将为**IStream**对象创建一个临时文件。 如果设置了此标志, 则还应设置 STGM_CREATE 和 STGM_READWRITE 标志。 
    
STGM_CREATE 
  
> 即使已经存在文件, 也要创建文件。 如果未设置_lpszFileName_参数, 则必须设置此标志和 STGM_DELETEONRELEASE。 如果设置了 STGM_CREATE, 则还必须设置 STGM_READWRITE 标志。 
    
STGM_DELETEONRELEASE 
  
> 释放**IStream**对象时, 将删除该文件。 如果未设置_lpszFileName_参数, 则必须设置此标志和 STGM_CREATE。 
    
STGM_READ 
  
> 将使用只读访问权限创建或打开文件。 
    
STGM_READWRITE 
  
> 将使用读/写权限创建或打开文件。 如果未设置此标志, 则不得设置 STGM_CREATE 标志。 
    
 _lpszFileName_
  
> 实时**OpenStreamOnFile**为其初始化**IStream**对象的文件的文件名, 包括路径和扩展名。 如果设置了 SOF_UNIQUEFILENAME 标志, 则_lpszFileName_包含要在其中创建临时文件的目录的路径。 如果_lpszFileName_为 NULL, 则**OpenStreamOnFile**从系统中获取适当的路径, 并且必须设置 STGM_CREATE 和 STGM_DELETEONRELEASE 标志。 
    
 _lpszPrefix_
  
> 实时**OpenStreamOnFile**用于初始化**IStream**对象的文件名的前缀。 如果设置, 则前缀必须包含三个以上的字符。 如果_lpszPrefix_为 NULL, 则使用前缀 "SOF"。 
    
 _lppStream_
  
> 排除指向公开**IStream**接口的对象的指针的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。 
    
MAPI_E_NO_ACCESS 
  
> 由于用户权限不足或无法修改只读文件, 无法访问文件。 
    
MAPI_E_NOT_FOUND 
  
> 指定的文件不存在。
    
## <a name="remarks"></a>注解

**OpenStreamOnFile**函数有两个重要的用途, 它们由 SOF_UNIQUEFILENAME 标志的设置加以区分。 如果未设置此标志, 则**OpenStreamOnFile**将在现有文件上打开**IStream**对象, 例如将其内容复制到使用 IStream 的附件的**PR_ATTACH_DATA_BIN** ([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md)) 属性。 **:: CopyTo**方法。 在这种情况下, _lpszFileName_参数指定文件的路径和文件名。 
  
设置 SOF_UNIQUEFILENAME 后, **OpenStreamOnFile**将创建一个临时文件, 用于保存**IStream**对象的数据。 在此用法中, _lpszFileName_参数可以选择指定要在其中创建文件的目录的路径, 并且_lpszPrefix_参数可以选择为文件名指定前缀。 
  
当调用客户端应用程序或服务提供程序完成了**IStream**对象时, 它应通过调用 OLE **IStream:: Release**方法来释放它。 
  
MAPI 使用_lpAllocateBuffer_和_lpFreeBuffer_指向的函数来实现大多数内存分配和释放, 尤其是在调用对象接口 (如[IMAPIProp::) 时分配供客户端应用程序使用的内存。GetProps](imapiprop-getprops.md)和[IMAPITable:: QueryRows](imapitable-queryrows.md)。 
  
## <a name="notes-to-callers"></a>给调用方的说明

SOF_UNIQUEFILENAME 标志用于创建具有邮件系统特有名称的临时文件。 如果设置了此标志, 则_lpszFileName_参数指定临时文件的路径, _lpszPrefix_参数包含文件名的前缀字符。 构造的文件名为<prefix>HHHH。TMP, 其中 HHHH 是一个十六进制数。 如果_lpszFileName_为 NULL, 则将在从 Windows 函数**GetTempPath**返回的临时文件目录中创建文件; 如果未指定临时文件目录, 则将在当前目录中创建文件。 
  
如果未设置 SOF_UNIQUEFILENAME 标志, 则将忽略_lpszPrefix_ , 并且_lpszFileName_应包含要打开或创建的文件的完全限定路径和文件名。 将根据在_ulFlags_中设置的其他标志打开或创建文件。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|文件 .cpp  <br/> |WriteAttachStreamToFile  <br/> |MFCMAPI 使用**OpenStreamOnFile**方法打开文件上的流, 以便可以向其写入附件。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

