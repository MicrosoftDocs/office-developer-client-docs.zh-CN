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
ms.openlocfilehash: 8c246968dcac719a8ee8177e20e802f9c7033435
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776570"
---
# <a name="openstreamonfile"></a>OpenStreamOnFile

  
  
**适用于**： Outlook 
  
分配并初始化 OLE **IStream**对象，以访问文件的内容。 此函数采用 ANSI 字符串所推荐的文件名称，包括的路径和文件扩展名，因此，使用此函数， [OpenStreamOnFileW](openstreamonfilew.md)，Unicode 版本。
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiutil.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
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
  
> [in]指向[MAPIAllocateBuffer](mapiallocatebuffer.md)函数，以用于分配内存。 
    
 _lpFreeBuffer_
  
> [in]指向[MAPIFreeBuffer](mapifreebuffer.md)函数，以用于释放内存。 
    
 _ulFlags_
  
> [in]位掩码的标志用于控制创建或打开该文件的访问通过 OLE **IStream**对象。 可以设置以下标志： 
    
SOF_UNIQUEFILENAME 
  
> 旨在为**IStream**对象创建一个临时文件。 如果设置此标志，还应设置 STGM_CREATE 和 STGM_READWRITE 标志。 
    
STGM_CREATE 
  
> 文件是以创建即使已存在。 如果未设置_lpszFileName_参数，必须设置此标志和 STGM_DELETEONRELEASE。 如果设置 STGM_CREATE，还必须设置 STGM_READWRITE 标志。 
    
STGM_DELETEONRELEASE 
  
> 文件是要删除在释放**IStream**对象时。 如果未设置_lpszFileName_参数，必须设置此标志和 STGM_CREATE。 
    
STGM_READ 
  
> 文件是要创建或打开具有只读访问权限。 
    
STGM_READWRITE 
  
> 文件是要创建或打开具有读/写权限。 如果未设置此标志，STGM_CREATE 标志必须不设置之一。 
    
 _lpszFileName_
  
> [in]文件名，包括路径和为其**OpenStreamOnFile**初始化**IStream**对象的文件扩展名。 如果设置了 SOF_UNIQUEFILENAME 标志， _lpszFileName_包含要在其中创建临时文件的目录的路径。 如果_lpszFileName_为 NULL，则**OpenStreamOnFile**在系统中，获取适当的路径，且必须设置 STGM_CREATE 和 STGM_DELETEONRELEASE 标志。 
    
 _lpszPrefix_
  
> [in]用于在其**OpenStreamOnFile**初始化**IStream**对象的文件名的前缀。 如果设置，前缀必须包含不能超过三个字符。 如果_lpszPrefix_为 NULL，则使用"SOF"的前缀。 
    
 _lppStream_
  
> [输出]为指向对象公开的**IStream**接口的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。 
    
MAPI_E_NO_ACCESS 
  
> 由于用户权限不足，无法访问文件或因为无法修改只读文件。 
    
MAPI_E_NOT_FOUND 
  
> 指定的文件不存在。
    
## <a name="remarks"></a>说明

**OpenStreamOnFile**函数有两个重要的用途，可分辨由 SOF_UNIQUEFILENAME 标志的设置。 **OpenStreamOnFile**时未设置此标志，打开现有文件，例如，以将其内容复制到使用**IStream 附件的**PR_ATTACH_DATA_BIN** ([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md)) 属性**IStream**对象:: CopyTo**方法。 在这种情况下_lpszFileName_参数指定的路径和文件的文件名。 
  
当设置 SOF_UNIQUEFILENAME 时， **OpenStreamOnFile**创建临时文件来保存**IStream**对象的数据。 对于此用法， _lpszFileName_参数 （可选） 指定的目录的文件是要创建并_lpszPrefix_参数可以选择指定的文件名的前缀的路径。 
  
完成呼叫的客户端应用程序或服务提供商后与**IStream**对象，它应通过调用 OLE **IStream::Release**方法来进行释放。 
  
MAPI 使用所指的_lpAllocateBuffer_和_lpFreeBuffer_对于大多数内存分配和释放，尤其是用于客户端应用程序分配内存，调用对象接口，如[IMAPIProp 时的功能：GetProps](imapiprop-getprops.md)和[IMAPITable::QueryRows](imapitable-queryrows.md)。 
  
## <a name="notes-to-callers"></a>给调用方的说明

SOF_UNIQUEFILENAME 标志用于创建特定于邮件系统名称的临时文件。 如果设置此标志， _lpszFileName_参数指定的路径的临时文件和_lpszPrefix_参数包含前缀字符的文件名。 构造的文件名是<prefix>HHHH。TMP，其中 HHHH 是一个十六进制数字。 如果_lpszFileName_为 NULL，则将将从 Windows 函数**GetTempPath**，返回的临时文件目录或当前目录中创建文件，如果已指定没有临时文件目录。 
  
如果未设置 SOF_UNIQUEFILENAME 标志，则会忽略_lpszPrefix_ ，并且_lpszFileName_应包含的完全限定的路径和文件名的文件创建或打开。 将打开该文件，或创建基于其他_ulFlags_中设置的标志。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|File.cpp  <br/> |WriteAttachStreamToFile  <br/> |MFCMAPI 使用**OpenStreamOnFile**方法打开文件流，因此附件可以写出到它。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

