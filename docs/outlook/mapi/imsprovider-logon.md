---
title: IMSProviderLogon
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMSProvider.Logon
api_type:
- COM
ms.assetid: 890d9cbe-3570-4cf0-aeae-667c0e5ba181
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 9c7f62c69c7a06f7ca0e4bfddcf789cddc536ea6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32309665"
---
# <a name="imsproviderlogon"></a>IMSProvider::Logon

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将 MAPI 记录到邮件存储提供程序的一个实例上。
  
```cpp
HRESULT Logon(
  LPMAPISUP lpMAPISup,
  ULONG_PTR ulUIParam,
  LPSTR lpszProfileName,
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  ULONG ulFlags,
  LPCIID lpInterface,
  ULONG FAR * lpcbSpoolSecurity,
  LPBYTE FAR * lppbSpoolSecurity,
  LPMAPIERROR FAR * lppMAPIError,
  LPMSLOGON FAR * lppMSLogon,
  LPMDB FAR * lppMDB
);
```

## <a name="parameters"></a>参数

 _lpMAPISup_
  
> 实时指向邮件存储区的当前 MAPI 支持对象的指针。
    
 _ulUIParam_
  
> 实时此方法显示的任何对话框或窗口的父窗口的句柄。 
    
 _lpszProfileName_
  
> 实时指向包含要用于存储提供程序登录的配置文件的名称的字符串的指针。 此字符串可以显示在对话框中, 将其写出到日志文件中, 或简单地忽略。 如果在_ulFlags_参数中设置了 MAPI_UNICODE 标志, 则它必须采用 Unicode 格式。 
    
 _cbEntryID_
  
> 实时由_lpEntryID_参数指向的条目标识符的大小 (以字节为单位)。 
    
 _lpEntryID_
  
> 实时指向邮件存储区的条目标识符的指针。 在_lpEntryID_中传递**null**指示尚未选择邮件存储, 并且可以显示使用户能够选择邮件存储的对话框。 
    
 _ulFlags_
  
> 实时用于控制登录执行方式的标志的位掩码。 可以设置以下标志:
    
MAPI_DEFERRED_ERRORS 
  
> 即使基础对象对调用实现不可用, 也允许该调用成功。 如果该对象不可用, 则对该对象的后续调用可能会引发错误。
    
MAPI_UNICODE 
  
> 传入的字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE, 则字符串将采用 ANSI 格式。
    
MDB_NO_DIALOG 
  
> 阻止显示登录对话框。 如果设置了此标志, 如果登录不成功, 则返回错误值 MAPI_E_LOGON_FAILED。 如果未设置此标志, 则邮件存储提供程序可以提示用户更正名称或密码、插入磁盘或执行与存储建立连接所需的其他操作。
    
MDB_NO_MAIL 
  
> 邮件存储不应用于发送或接收邮件。 此标志通知 mapi 不通知 mapi 后台处理程序正在打开此邮件存储。 如果设置了此标志, 且邮件存储与传输提供程序紧密结合, 则提供程序不需要调用[IMAPISupport:: SpoolerNotify](imapisupport-spoolernotify.md)方法。 
    
MDB_TEMPORARY 
  
> 在存储区上记录, 以便可以从 "配置文件" 部分以编程方式检索信息, 而无需使用对话框。 此标志指示 MAPI 存储不会添加到邮件存储库表中, 并且无法永久成为存储。 如果设置了此标志, 则邮件存储提供程序无需调用[IMAPISupport:: ModifyProfile](imapisupport-modifyprofile.md)方法。 
    
MDB_WRITE 
  
> 请求读取/写入权限。
    
 _lpInterface_
  
> 实时指向要登录到的邮件存储区的接口标识符 (IID) 的指针。 传递**null**表示将返回邮件存储 ( [IMsgStore](imsgstoreimapiprop.md)) 的 MAPI 接口。 也可以将_lpInterface_参数设置为邮件存储区的相应接口的标识符 (例如, IID_IUnknown 或 IID_IMAPIProp)。 
    
 _lpcbSpoolSecurity_
  
> 排除指向存储提供程序在其中返回_lppbSpoolSecurity_参数中的验证数据的大小 (以字节为单位) 的变量的指针。 
    
 _lppbSpoolSecurity_
  
> 排除指向指向返回的验证数据的指针的指针。 提供此验证数据是为了使[IMSProvider:: SpoolerLogon](imsprovider-spoolerlogon.md)方法可以将 MAPI 后台处理程序记录到与邮件存储提供程序相同的存储中。 
    
 _lppMAPIError_
  
> 排除指向包含错误的版本、组件和上下文信息的返回的[MAPIERROR](mapierror.md)结构的指针 (如果有)。 如果没有要返回的**MAPIERROR**结构, 则可以将_lppMAPIError_参数设置为**null** 。 
    
 _lppMSLogon_
  
> 排除指向邮件存储区登录对象的指针, MAPI 将登录到该对象。
    
 _lppMDB_
  
> 排除指向指向要登录到的 MAPI 后台处理程序和客户端应用程序的邮件存储对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。
    
MAPI_E_FAILONEPROVIDER 
  
> 此提供程序无法登录, 但此错误不应禁用该服务。 
    
MAPI_E_LOGON_FAILED 
  
> 无法建立登录会话。
    
MAPI_E_UNCONFIGURED 
  
> 配置文件中包含的信息不足, 无法完成登录。 返回此值时, MAPI 会调用邮件存储提供程序的消息服务入口点函数。
    
MAPI_E_USER_CANCEL 
  
> 用户取消了操作, 通常是单击对话框中的 "**取消**" 按钮。 
    
MAPI_E_UNKNOWN_CPID 
  
> 未将服务器配置为支持客户端的代码页。
    
MAPI_E_UNKNOWN_LCID 
  
> 未将服务器配置为支持客户端的区域设置信息。
    
MAPI_W_ERRORS_RETURNED 
  
> 调用成功, 但邮件存储区提供程序有可用的错误信息。 返回此警告时, 应以成功的方式处理该调用。 若要测试此警告, 请使用**HR_FAILED**宏。 有关详细信息, 请参阅[使用宏进行错误处理](using-macros-for-error-handling.md)。 若要从提供程序获取错误消息, 请调用[IMAPISession:: GetLastError](imapisession-getlasterror.md)方法。 
    
## <a name="remarks"></a>注解

MAPI 调用**IMSProvider:: Logon**方法, 以执行获取对邮件存储区的访问所必需的大部分处理过程。 邮件存储提供程序验证访问特定存储区所需的任何用户凭据, 并返回 MAPI 后台处理程序和客户端应用程序可以登录到的_lppMDB_参数中的邮件存储对象。 
  
除了返回的用于客户端和 MAPI 后台处理程序的邮件存储对象之外, 该提供程序还返回邮件存储登录对象, 以便 MAPI 在控制打开的存储区时使用。 邮件存储登录对象和邮件存储对象应紧密链接到邮件存储提供程序中, 以便每个对象都能影响另一个对象。 store 对象和 logon 对象的使用应相同;登录对象和 store 对象之间应存在一对一的对应关系, 这样, 这些对象就像是一个公开两个接口的对象一样。 这两个对象也应一起创建并一起释放。 
  
mapi 支持对象 (由 mapi 创建并在_lpMAPISup_参数中传递给提供程序) 提供了对 MAPI 中提供程序所需的函数的访问。 这些函数包括保存和检索配置文件信息、访问通讯簿等的函数。 对于打开的每个存储, _lpMAPISup_指针可能有所不同。 在登录后处理邮件存储区的呼叫时, 存储提供程序应使用特定于该存储的_lpMAPISup_变量。 对于打开邮件存储区并在创建邮件存储登录对象时成功的任何**登录**呼叫, 提供程序必须保存指向 store Logon 对象中的 MAPI 支持对象的指针, 并且必须调用[IUnknown:: AddRef](https://msdn.microsoft.com/library/ms691379%28v=VS.85%29.aspx)方法以添加对的引用支持对象。 
  
如果提供程序在**登录**呼叫过程中显示对话框, 则应使用_ulUIParam_参数。 但是, 如果_ulFlags_包含 MDB_NO_DIALOG 标志, 则不应显示对话框。 如果需要调用用户界面, 但_ulFlags_不允许, 或者如果由于其他原因而无法显示用户界面, 则提供程序应返回 MAPI_E_LOGON_FAILED。 如果**登录**显示一个对话框, 并且用户取消了登录, 则通常通过单击对话框的 "**取消**" 按钮, 提供程序应返回 MAPI_E_USER_CANCEL。 
  
_lpEntryID_参数可以是**null** , 也可以指向此邮件存储之前创建的已解包的存储条目标识符。 如果_lpEntryID_指向一个已断开的条目标识符, 则该条目标识符可以来自多个位置之一: 
  
- 它可以是存储提供程序之前作为**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性打包并写入到配置文件节中的条目标识符。
    
- 它可以是提供程序之前作为**PR_STORE_ENTRYID** ([PidTagStoreEntryId](pidtagstoreentryid-canonical-property.md)) 属性进行包装并返回给呼叫客户端的条目标识符。 
    
- 它可以是提供程序之前作为邮件存储对象的**PR_ENTRYID**属性进行包装并返回给呼叫客户端的条目标识符。 
    
在上述任一情况下, 可能会在与当前使用的计算机不同的计算机上创建条目标识符。
  
如果_lpEntryID_不**为 null**, 则它应包含标识和定位邮件存储区所需的所有信息。 此信息可以包括网络卷名、电话号码、用户帐户名等等。 如果使用条目标识符中的数据无法建立与存储区的连接, 则存储提供程序应显示一个对话框, 使用户能够选择要打开的存储。 对话框可能是必需的, 例如, 如果服务器已重命名、帐户名称已更改或部分网络不可用。
  
如果_lpEntryID_为**null**, 则尚未选择要使用的邮件存储区。 如果提供程序支持用于指定存储的其他方法, 则该提供程序仍可以访问存储, 而不显示对话框。 例如, 提供程序可以检查其初始化文件, 也可以查找配置中放置在其或其消息服务的配置文件部分中的其他属性。
  
如果提供程序发现所有必需的信息都不在配置文件中, 则应返回 MAPI_E_UNCONFIGURED。 然后, MAPI 将调用提供程序的邮件服务入口点函数, 以使用户能够选择存储, 甚至可以创建一个存储, 并根据需要输入帐户名称和密码。 MAPI 为新存储自动创建一个新的配置文件部分;此新的配置文件节可以是临时的, 也可以是永久的, 具体取决于它的添加方式。 如果存储提供程序调用**IMAPISupport:: ModifyProfile**方法, 则新的配置文件节将成为永久的, 并将该存储区添加到[IMAPISession:: GetMsgStoresTable](imapisession-getmsgstorestable.md)方法返回的邮件存储列表中。 
  
_lpInterface_参数指定新打开的存储对象所需的接口的 IID。 在_lpInterface_中传递**null**指定 MAPI 邮件存储区接口 ( **IMsgStore**) 是必需的。 传递邮件存储区对象 IID_IMsgStore 还指定**IMsgStore**是必需的。 如果在_lpInterface_中传递 IID_IUnknown, 则提供程序应使用从[IUnknown](https://msdn.microsoft.com/library/ms680509%28v=VS.85%29.aspx)派生的任何接口打开存储, 以最适合提供程序的接口 (同样, 这通常是**IMsgStore**)。 当传递 IID_IUnknown 时, 调用实现使用[IUnknown:: QueryInterface](https://msdn.microsoft.com/library/ms682521%28v=VS.85%29.aspx)方法在存储打开操作成功后选择接口。 
  
**IMSProvider:: Logon**调用应返回足够的信息, 如访问存储区的存储和凭据的路径, 以允许 MAPI 后台处理程序登录到存储提供程序的同一存储, 而不显示对话框。 _lpcbSpoolSecurity_和_lppbSpoolSecurity_参数用于返回此信息。 提供程序通过在[MSProviderInit](msproviderinit.md)函数的_lpfAllocateBuffer_参数中传递指向缓冲区的指针来为此数据分配内存;提供程序在_lpcbSpoolSecurity_中放置此缓冲区的大小。 
  
MAPI 在适当的时候释放此缓冲区。 如果 MAPI 后台处理程序登录到存储可以从 "配置文件" 部分的信息单独完成, 则提供程序可以在_lppbSpoolSecurity_中返回 null, 而在_lpcbSpoolSecurity_中返回的信息大小为0。 MAPI 后台处理程序登录与存储登录过程中的过程不同, 它是由于包含传递的信息的缓冲区在进程之间进行复制, 因此与存储提供程序进程相比, MAPI 后台处理程序进程的内存可能不在同一位置。 因此, 提供程序不应将地址放入此缓冲区中。 有关 MAPI 后台处理程序登录的详细信息, 请参阅[IMSProvider:: SpoolerLogon](imsprovider-spoolerlogon.md)方法。 
  
大多数存储提供程序使用在_lpMAPISup_参数中传递的支持对象的[IMAPISession:: OpenProfileSection](imapisession-openprofilesection.md)方法来保存和检索用户凭据和选项。 **OpenProfileSection**使存储提供程序能够在 profile 节中保存其他任意信息, 并将其与特定资源相关联。 例如, 存储提供程序可以保存与资源相关联的用户帐户名和密码, 以及访问该资源所需的任何路径或其他信息。 
  
属性标识符0x6600 到0x67FF 的属性是可供提供程序用来在 profile 节中存储私有数据的安全属性。 有关 profile 部分对象中的属性使用的详细信息, 请参阅[IProfSect: IMAPIProp](iprofsectimapiprop.md)方法。 
  
除了标识符0x6600 到0x67FF 的属性中的任何专用数据之外, 存储提供程序还应在其 profile 节中提供**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性的信息。 它应放在**PR_DISPLAY_NAME**中, 提供程序本身的显示名称 (一个标识字符串 (例如 "Microsoft 个人信息存储"), 以便用户可以将此邮件存储区与他们可能有权访问的其他人区分开来自。 **PR_DISPLAY_NAME**通常包含服务器名称、用户帐户名称或路径。 
  
某些配置文件节属性在邮件存储表中可见;其他人在安装、安装和配置 MAPI 子系统期间可见。 提供程序通常会为一个新的配置文件部分提供这些可见属性的信息, 该部分还不包括保存的凭据或私有信息, 并且在发现属性信息已更改时。 有关配置文件节的详细信息, 请参阅[IMAPISupport:: OpenProfileSection](imapisupport-openprofilesection.md)。
  
在用户成功登录并返回 MAPI 之前, 存储提供程序应为资源的状态行创建属性的数组并调用[IMAPISupport:: ModifyStatusRow](imapisupport-modifystatusrow.md)方法。 
  
 打开已为当前 MAPI 会话打开的邮件存储的**登录**调用将跳过上述大部分处理过程。 这些呼叫不会创建状态行、返回邮件存储区登录对象、调用**AddRef**的 mapi 支持对象或返回 mapi 后台处理程序登录的数据。 这些调用确实返回 S_OK, 并返回包含所请求的接口的邮件存储对象。 
  
若要检测此类调用, 提供程序应在已为此提供程序对象打开的存储的邮件存储区提供程序对象中维护一个列表。 在处理**登录**呼叫时, 提供程序应扫描此打开存储的列表, 并确定要登录到的存储是否已打开。 如果是这样, 则无需选中用户凭据, 并且应尽可能避免显示对话框 (如果可能)。 如果必须显示对话框, 则提供程序应检查返回的信息, 以查看是否已再次打开存储区。 此外, 提供程序应在**登录**呼叫处理开始时使用_lpEntryID_检查是否存在重复的空缺。 
  
访问打开存储的**登录**呼叫的标准处理方式如下所示: 
  
1. 如果请求的新接口与现有存储区的接口相同, 则存储提供程序将对现有 store 对象调用**AddRef** 。 否则, 它调用**QueryInterface**以获取新接口。 如果存储区不支持新接口, 则提供程序应返回错误值 MAPI_E_INTERFACE_NOT_SUPPORTED。 
    
2. 提供程序返回指向_lppMDB_中现有 store 对象的所需接口的指针。
    
3. 提供程序在_lppMSLogon_中返回**null** 。
    
4. 提供程序不应打开在呼叫中传递的支持对象的配置文件。 此外, 它不应注册提供程序的唯一标识符、注册状态行或返回 MAPI 后台处理程序登录数据。
    
5. 提供程序不应调用支持对象的**AddRef** , 因为它不需要指向对象的指针。 
    
只要有可能, 提供程序就会为**登录**调用返回适当的错误和警告字符串, 因为这样做可大大减轻用户在决定为什么不起作用的原因。 若要返回这些字符串, 提供程序将设置**MAPIERROR**结构中的成员。 MAPI 查找、使用和释放**MAPIERROR**结构 (如果提供程序返回)。 
  
应使用在**MSProviderInit**调用的_lpfAllocateBuffer_中传递的缓冲区分配此**MAPIERROR**结构的内存。 如果在**登录** _ulFlags_中设置了 MAPI_UNICODE, 则返回的结构中包含的任何错误字符串都应采用 Unicode 格式; 否则, 它们应在 ANSI 字符集中。 
  
对于从**登录**返回的大多数错误值, MAPI 都会禁用失败的提供程序所属的邮件服务。 mapi 在 mapi 会话的有效期内不会调用任何属于这些服务的提供程序。 相比之下, 当**logon**从其登录中返回 MAPI_E_FAILONEPROVIDER 错误值时, MAPI 不会禁用该提供程序所属的邮件服务。 如果遇到不保证在会话生命周期内禁用整个服务的错误, 则**登录**应返回 MAPI_E_FAILONEPROVIDER。 例如, 当提供程序不允许显示用户界面且必需的密码不可用时, 该提供程序可能会返回此错误。 
  
如果提供程序从其登录返回 MAPI_E_UNCONFIGURED, 则 MAPI 将调用提供程序的邮件服务条目功能, 然后重试该登录。 MAPI 将 MSG_SERVICE_CONFIGURE 作为上下文, 使服务有机会对自身进行配置。 如果客户端已选择允许登录时使用用户界面, 则服务可以显示其配置属性表, 以便用户可以输入配置信息。
  
## <a name="see-also"></a>另请参阅



[IMAPISession::GetMsgStoresTable](imapisession-getmsgstorestable.md)
  
[IMAPISession::OpenMsgStore](imapisession-openmsgstore.md)
  
[IMAPISession::OpenProfileSection](imapisession-openprofilesection.md)
  
[IMAPISupport::ModifyProfile](imapisupport-modifyprofile.md)
  
[IMAPISupport::ModifyStatusRow](imapisupport-modifystatusrow.md)
  
[IMsgStore : IMAPIProp](imsgstoreimapiprop.md)
  
[IMSProvider::SpoolerLogon](imsprovider-spoolerlogon.md)
  
[IProfSect : IMAPIProp](iprofsectimapiprop.md)
  
[MAPIERROR](mapierror.md)
  
[MSProviderInit](msproviderinit.md)
  
[IMSProvider : IUnknown](imsprovideriunknown.md)

