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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 9c7f62c69c7a06f7ca0e4bfddcf789cddc536ea6
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25386563"
---
# <a name="imsproviderlogon"></a>IMSProvider::Logon

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
日志 MAPI 到消息存储提供程序的一个实例。
  
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
  
> [in]一个指向当前的 MAPI 支持的消息存储对象。
    
 _ulUIParam_
  
> [in]该方法显示的任何对话框或窗口的父窗口的句柄。 
    
 _lpszProfileName_
  
> [in]一个指向一个字符串，包含要用于存储提供程序登录的配置文件的名称。 可以显示在对话框中，写入日志文件，或只忽略此字符串。 如果_ulFlags_参数中设置 MAPI_UNICODE 标志，它必须是以 Unicode 格式。 
    
 _cbEntryID_
  
> [in]以字节为单位_lpEntryID_参数指向的项标识符的大小。 
    
 _lpEntryID_
  
> [in]指向消息存储库的项标识符的指针。 _LpEntryID_中传递**null**指示尚未选择的消息存储，并且可以提供让用户能够选择的消息存储的对话框。 
    
 _ulFlags_
  
> [in]位掩码的标志，控制如何执行登录。 可以设置以下标志：
    
MAPI_DEFERRED_ERRORS 
  
> 若要成功执行，即使基础对象不可用的呼叫的实现，即允许该呼叫。 如果对象不可用，对对象的后续调用可能会引发一个错误。
    
MAPI_UNICODE 
  
> 传入的字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 的字符串是以 ANSI 格式。
    
MDB_NO_DIALOG 
  
> 阻止登录对话框的显示。 如果设置此标志，如果登录失败，则返回错误值 MAPI_E_LOGON_FAILED。 如果未设置此标志，消息存储提供程序可以提示用户正确的名称或密码，插入磁盘，或执行其他操作所需建立连接到存储区。
    
MDB_NO_MAIL 
  
> 消息存储不应用于发送或接收邮件。 标志信号 MAPI 不以通知 MAPI 后台处理程序打开的时此消息存储。 如果设置此标志，与传输提供程序紧密耦合的消息存储，则不需要调用[IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md)方法提供程序。 
    
MDB_TEMPORARY 
  
> 对存储日志，以便从配置文件部分中，以编程方式检索信息不使用的对话框。 此标志指示 MAPI 存储是不是要添加到消息存储表和存储无法进行永久。 如果设置此标志，消息存储提供程序不需要调用[IMAPISupport::ModifyProfile](imapisupport-modifyprofile.md)方法。 
    
MDB_WRITE 
  
> 请求读/写权限。
    
 _lpInterface_
  
> [in]指向要登录到的邮件存储区的接口标识符 (IID) 的指针。 传递**null**指示返回的消息存储 ( [IMsgStore](imsgstoreimapiprop.md)) 的 MAPI 界面。 _LpInterface_参数还可以设置为消息存储 （例如，IID_IUnknown 或 IID_IMAPIProp） 的适当的接口的标识符。 
    
 _lpcbSpoolSecurity_
  
> [输出]指向在其中存储提供程序返回的大小，以字节为单位的_lppbSpoolSecurity_参数中的验证数据变量的指针。 
    
 _lppbSpoolSecurity_
  
> [输出]指向该指针指向返回的验证数据的指针。 以便[IMSProvider::SpoolerLogon](imsprovider-spoolerlogon.md)方法可以登录到同一个存储 MAPI 后台处理程序的消息存储提供程序提供此验证数据。 
    
 _lppMAPIError_
  
> [输出]指向返回[MAPIERROR](mapierror.md)结构，如果有，其中包含的错误的版本、 组件及上下文信息的指针的指针。 如果不没有返回任何**MAPIERROR**结构， _lppMAPIError_参数可以设置为**null** 。 
    
 _lppMSLogon_
  
> [输出]指向该指针指向邮件存储 MAPI 登录到的登录对象。
    
 _lppMDB_
  
> [输出]指向该指针指向邮件存储 MAPI 后台处理程序和客户端应用程序登录到的对象。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
MAPI_E_FAILONEPROVIDER 
  
> 此提供程序不能登录，但不是服务应禁用此错误。 
    
MAPI_E_LOGON_FAILED 
  
> 无法建立登录会话。
    
MAPI_E_UNCONFIGURED 
  
> 配置文件不包含登录后，若要完成的足够信息。 返回此值时，MAPI 调用的消息存储提供程序的消息服务入口点函数。
    
MAPI_E_USER_CANCEL 
  
> 用户取消操作，通常通过单击对话框中的**取消**按钮。 
    
MAPI_E_UNKNOWN_CPID 
  
> 将服务器不配置为支持客户端的代码页。
    
MAPI_E_UNKNOWN_LCID 
  
> 将服务器不配置为支持客户端的区域设置信息。
    
MAPI_W_ERRORS_RETURNED 
  
> 调用成功，但消息存储提供程序已经可用的错误信息。 返回此警告时，应处理呼叫为成功。 若要测试此警告，请使用**HR_FAILED**宏。 有关详细信息，请参阅[使用宏的错误处理](using-macros-for-error-handling.md)。 要从提供程序获取错误的信息，请调用[IMAPISession::GetLastError](imapisession-getlasterror.md)方法。 
    
## <a name="remarks"></a>说明

MAPI 调用**IMSProvider::Logon**方法执行大部分获取的消息存储访问所需的处理。 消息存储提供程序验证任何需要访问特定存储和 MAPI 后台处理程序和客户端应用程序可以登录到_lppMDB_参数中返回的消息存储对象的用户凭据。 
  
除了为客户端和 MAPI 后台处理程序使用返回的消息存储对象，提供程序也会返回 MAPI 用于控制在打开的存储的消息存储登录对象。 消息存储登录对象和消息存储对象应紧密链接内的消息存储提供程序以便如何影响其他。 使用的存储对象和登录对象应相同;应一一对应登录对象之间的存储对象，以便对象就像它们是公开两个接口的一个对象。 两个对象应还创建组合在一起和释放在一起。 
  
MAPI 支持对象，由 MAPI 和传递给_lpMAPISup_参数中的提供程序提供访问的提供程序需要的 MAPI 中的功能。 包括函数的保存和检索配置文件信息、 访问通讯簿，等等。 _LpMAPISup_指针可以打开每个存储的不同。 时处理呼叫消息存储登录后，存储提供程序应使用的特定于存储_lpMAPISup_变量。 提供程序的任何**登录**调用，以打开的消息存储并成功创建消息存储登录对象，必须将指针保存到存储登录对象中的 MAPI 支持对象和必须调用[IUnknown::AddRef](https://msdn.microsoft.com/library/ms691379%28v=VS.85%29.aspx)方法添加的引用支持的对象。 
  
如果提供程序**登录**呼叫期间显示对话框，则应使用_ulUIParam_参数。 但是，如果_ulFlags_包含 MDB_NO_DIALOG 标志应不显示对话框。 如果用户界面需要调用但_ulFlags_不允许使用它，或者如果其他原因无法显示用户界面，提供程序应返回 MAPI_E_LOGON_FAILED。 如果**登录**显示一个对话框，并且用户取消了登录，通常通过单击对话框的**取消**按钮，提供程序应返回 MAPI_E_USER_CANCEL。 
  
_LpEntryID_参数可以为**null**或指向解包的存储项的标识符此消息存储以前创建的。 如果_lpEntryID_指向解包的条目标识符，该条目标识符可来自多个位置之一： 
  
- 它可以是存储提供程序以前自动换行，并记作为**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性配置文件一节的项标识符。
    
- 它可以是提供程序以前自动换行，并返回到**PR_STORE_ENTRYID** ([PidTagStoreEntryId](pidtagstoreentryid-canonical-property.md)) 属性以调用客户端的项标识符。 
    
- 它可以是提供程序以前自动换行，并作为消息存储对象的**PR_ENTRYID**属性返回到调用客户端的项标识符。 
    
在上述任一情况下，很可能比当前正在使用不同的计算机上创建的项标识符的。
  
当_lpEntryID_不**为 null**时，它应包含所有所需确定并找到消息存储库的信息。 此信息可以包括网络卷名称、 电话号码、 用户帐户名和等等。 如果无法建立到商店连接，通过使用中的项标识符的数据，存储提供程序应显示一个对话框，使用户能够选择要打开的存储。 一个对话框，可能需要，例如，如果已重命名服务器、 已更改的帐户名称，或网络的部分不可用。
  
**Null** _lpEntryID_后，要使用的消息存储具有尚未选择。 提供程序仍可以访问存储区，而不显示一个对话框，如果它支持进一步的方法，以指定的存储。 例如，提供程序可以检查其初始化文件，或者它可以查找放置在其或其消息服务的配置文件配置处的一节中的其他属性。
  
如果提供程序查找所有所需的信息不在配置文件中，则应返回 MAPI_E_UNCONFIGURED。 MAPI 将呼叫提供商的消息服务入口点函数以允许用户选择一个存储区，或甚至创建一个，并以输入帐户名和密码，需要。 MAPI 将自动创建新的存储; 新配置文件节本节新配置文件可以是临时或永久，具体取决于添加的方式。 如果存储提供程序调用**IMAPISupport::ModifyProfile**方法时，新的配置文件部分会成为永久性并存储添加到[IMAPISession::GetMsgStoresTable](imapisession-getmsgstorestable.md)方法返回的消息存储的列表。 
  
_LpInterface_参数指定新打开的存储对象所需的接口的 IID。 在_lpInterface_传递**null**指定 MAPI 消息存储接口， **IMsgStore**，都要求。 传递消息存储对象，IID_IMsgStore，还指定**IMsgStore**都要求。 如果在_lpInterface_传递 IID_IUnknown，则提供程序应使用的任何接口派生打开存储[IUnknown](https://msdn.microsoft.com/library/ms680509%28v=VS.85%29.aspx)是最适用于提供程序 （同样，这通常是**IMsgStore**）。 当 IID_IUnknown 传递时，调用实现使用[IUnknown::QueryInterface](https://msdn.microsoft.com/library/ms682521%28v=VS.85%29.aspx)方法存储打开操作成功后，选择一个接口。 
  
**IMSProvider::Logon**呼叫应返回足够的信息，如存储和访问的存储，以允许 MAPI 后台处理程序登录到的存储提供程序实现，而无演示对话框中的同一存储的凭据的路径。 在_lpcbSpoolSecurity_和_lppbSpoolSecurity_参数用于返回此信息。 提供程序通过将指针传递到的缓冲区中的[MSProviderInit](msproviderinit.md)函数_lpfAllocateBuffer_参数，则此数据分配的内存提供程序置于_lpcbSpoolSecurity_此缓冲区的大小。 
  
MAPI 释放时相应此缓冲区。 如果表达配置文件部分中的信息，可以通过 MAPI 后台处理程序的登录到存储区，提供程序可以返回 null _lppbSpoolSecurity_和信息的大小以_lpcbSpoolSecurity_0 中。 MAPI 后台处理程序登录发生不同于存储登录; 进程的一部分包含传递的信息的缓冲区获取进程之间复制的因为它可能不是内存存储提供程序进程相同的 MAPI 后台处理程序过程的相同位置中。 因此，提供程序不应将地址放入此缓冲区中。 有关 MAPI 后台处理程序登录的详细信息，请参阅[IMSProvider::SpoolerLogon](imsprovider-spoolerlogon.md)方法。 
  
大多数存储提供程序使用[IMAPISession::OpenProfileSection](imapisession-openprofilesection.md)方法保存和检索用户凭据和选项的_lpMAPISup_参数中传递的支持对象。 **OpenProfileSection**使存储提供程序配置文件节中保存任意的其他信息，并将其与特定的资源关联。 例如，存储提供程序可以保存的用户帐户名和密码与资源和任何路径或访问该资源所需的其他信息关联。 
  
使用属性标识符通过 0x67FF 0x6600 属性是供自己使用配置文件各节中存储私有数据提供程序的安全属性。 有关使用配置文件部分对象中的属性的详细信息，请参阅[IProfSect: IMAPIProp](iprofsectimapiprop.md)方法。 
  
除了使用标识符通过 0x67FF 0x6600 属性中的任何私有数据，存储提供程序应提供其配置文件一节中**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性的信息。 它应置于**PR_DISPLAY_NAME**本身的提供程序的显示名称 — 标识字符串 （例如，"Microsoft 个人信息存储"），它们可以将此消息存储与其他人区分开来以便向用户显示他们可能具有访问权限自。 **PR_DISPLAY_NAME**通常包含服务器名称、 用户帐户名称或路径。 
  
可以看到消息存储表; 中一些配置文件的部分属性其他人都能看到期间安装程序、 安装和配置的 MAPI 子系统。 提供程序通常提供新的配置文件节，其尚未包含保存的凭据或私人信息和时它查找属性信息已更改这些可见属性这两个的信息。 有关配置文件节的详细信息，请参阅[IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md)。
  
成功登录用户和 MAPI 向返回之前之后, 的存储提供程序应创建的资源的状态行属性数组，并调用[IMAPISupport::ModifyStatusRow](imapisupport-modifystatusrow.md)方法。 
  
 打开当前的 MAPI 会话已打开的消息存储的**登录**呼叫跳过何种前面所述的处理。 这些呼叫不要创建状态行、 返回消息存储登录对象，对于 MAPI 支持对象，调用**AddRef**或 MAPI 后台处理程序登录为返回数据。 这些呼叫执行返回 S_OK 和返回与请求的接口的消息存储对象。 
  
若要检测此类呼叫，提供程序应该中存储的消息存储提供程序对象的列表为此提供程序对象已打开。 处理时**登录**呼叫，提供程序应扫描打开存储此列表，并确定要登录到的存储是否已打开。 如果是，用户凭据不需要检查并显示一个对话框，应避免，如果可能。 如果必须显示对话框，提供程序应检查返回的信息，以查看是否已打开存储第二次。 此外，提供程序应检查重复开口**登录**呼叫的开头使用_lpEntryID_处理。 
  
标准**登录**呼叫访问打开存储处理如下所示： 
  
1. 存储提供程序为现有的存储对象调用**AddRef** ，如果正在请求的新接口是与现有的存储的界面相同。 否则，它将调用**QueryInterface**获取新接口。 如果存储区不支持新的界面，提供程序应返回错误值 MAPI_E_INTERFACE_NOT_SUPPORTED。 
    
2. 提供程序返回到_lppMDB_中的现有存储对象的所需的接口的指针。
    
3. 提供程序在_lppMSLogon_返回**null** 。
    
4. 提供程序不应打开传入呼叫的支持对象的配置文件。 此外，它不应注册提供程序的唯一标识符，注册一个状态行中，或返回登录数据的 MAPI 后台处理程序。
    
5. 提供程序不应支持对象中，调用**AddRef** ，因为它不需要对对象的指针。 
    
只要有可能，提供程序应返回相应的错误和警告字符串**登录**呼叫，因为这样做会显著可减轻负担中确定为什么内容无法正常工作的用户。 若要返回这些字符串，提供程序设置**MAPIERROR**结构中的成员。 MAPI 查找和使用，如果提供程序返回释放**MAPIERROR**结构。 
  
应使用**MSProviderInit**呼叫_lpfAllocateBuffer_中传递的缓冲区分配此**MAPIERROR**结构的内存。 如果 MAPI_UNICODE 设置中**登录** _ulFlags;_ 否则，返回的结构中包含字符串应为 Unicode 格式任何错误，他们应的 ANSI 字符集字符中设置。 
  
对于大多数**登录**从返回的错误值，MAPI 禁用的失败提供程序所属的消息服务。 MAPI 将不会调用属于生命周期的 MAPI 会话这些服务的任何提供程序。 相比之下时**登录**其登录过程中返回 MAPI_E_FAILONEPROVIDER 错误值，, MAPI 不禁用邮件服务提供程序所属。 如果遇到错误，不保证禁用整个会话的生命周期服务，则**登录**应返回 MAPI_E_FAILONEPROVIDER。 例如，提供程序可能不允许的用户界面的显示和所需的密码将不可用时返回该错误。 
  
如果提供程序返回 MAPI_E_UNCONFIGURED 从其登录，MAPI 将调用提供程序的消息服务条目函数，然后重试登录。 MAPI 将 MSG_SERVICE_CONFIGURE 以使配置本身有机会的服务上下文。 如果客户端已经选择允许在登录的用户界面，该服务可以将其配置属性表，以便用户可以输入配置信息。
  
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

