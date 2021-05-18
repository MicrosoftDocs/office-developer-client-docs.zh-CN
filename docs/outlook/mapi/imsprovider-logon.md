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
  
将 MAPI 记录到邮件存储提供程序的一个实例。
  
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
  
> [in]指向邮件存储的当前 MAPI 支持对象的指针。
    
 _ulUIParam_
  
> [in]该方法显示的任何对话框或窗口的父窗口的句柄。 
    
 _lpszProfileName_
  
> [in]指向包含用于存储提供程序登录的配置文件的名称的字符串的指针。 此字符串可以在对话框中显示、写入或日志文件或忽略。 如果在  _ulFlags_ 参数中设置了 MAPI_UNICODE 标志，则它必须采用 Unicode 格式。 
    
 _cbEntryID_
  
> [in]  _lpEntryID_ 参数指向的条目标识符的大小（以字节为单位）。 
    
 _lpEntryID_
  
> [in]指向邮件存储的条目标识符的指针。 在 _lpEntryID_ 中传递 **null** 表示尚未选择邮件存储，并且会显示允许用户选择邮件存储的对话框。 
    
 _ulFlags_
  
> [in]控制如何执行登录的标志的位掩码。 可以设置以下标志：
    
MAPI_DEFERRED_ERRORS 
  
> 即使基础对象对调用实现不可用，也允许调用成功。 如果该对象不可用，则对该对象的后续调用可能会引发错误。
    
MAPI_UNICODE 
  
> 传入字符串采用 Unicode 格式。 如果未MAPI_UNICODE，则字符串采用 ANSI 格式。
    
MDB_NO_DIALOG 
  
> 禁止显示登录对话框。 如果设置此标志，则返回错误MAPI_E_LOGON_FAILED登录不成功时返回。 如果未设置此标志，则邮件存储提供程序可以提示用户更正名称或密码、插入磁盘或执行与存储建立连接所需的其他操作。
    
MDB_NO_MAIL 
  
> 邮件存储不应用于发送或接收邮件。 该标志指示 MAPI 不通知 MAPI 后台处理程序此邮件存储正在打开。 如果设置了此标志，并且邮件存储与传输提供程序紧密结合，则提供程序不需要调用 [IMAPISupport：：SpoolerNotify](imapisupport-spoolernotify.md) 方法。 
    
MDB_TEMPORARY 
  
> 记录存储，以便可以通过编程方式从配置文件部分检索信息，而无需使用对话框。 此标志指示 MAPI 不会将存储添加到邮件存储表，并且存储不能永久化。 如果设置了此标志，则消息存储提供程序无需调用 [IMAPISupport：：ModifyProfile](imapisupport-modifyprofile.md) 方法。 
    
MDB_WRITE 
  
> 请求读/写权限。
    
 _lpInterface_
  
> [in]指向接口标识符的 (IID) 供邮件存储登录。 传递 **null** 指示返回 [IMsgStore](imsgstoreimapiprop.md) (邮件存储) MAPI 接口。 _还可以将 lpInterface_ 参数设置为邮件存储的适当接口的标识符 (例如，IID_IUnknown 或 IID_IMAPIProp) 。 
    
 _lpcbSpoolSecurity_
  
> [out]指向存储提供程序在  _lppbSpoolSecurity_ 参数中返回验证数据的大小（以字节为单位）的变量的指针。 
    
 _lppbSpoolSecurity_
  
> [out]指向返回的验证数据的指针的指针。 提供此验证数据，以便 [IMSProvider：：SpoolerLogon](imsprovider-spoolerlogon.md) 方法可以将 MAPI 后台处理程序记录到与消息存储提供程序相同的存储。 
    
 _lppMAPIError_
  
> [out]指向返回的 [MAPIERROR](mapierror.md) 结构的指针（如果有）的指针，其中包含错误的版本、组件和上下文信息。 如果没有要返回的 **MAPIERROR** 结构，可以将 _lppMAPIError_ 参数设置为 null。 
    
 _lppMSLogon_
  
> [out]指向指向 MAPI 要登录的消息存储登录对象的指针的指针。
    
 _lppMDB_
  
> [out]指向 MAPI 后台处理程序和客户端应用程序要登录的消息存储对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。
    
MAPI_E_FAILONEPROVIDER 
  
> 此提供程序无法登录，但此错误不应禁用该服务。 
    
MAPI_E_LOGON_FAILED 
  
> 无法建立登录会话。
    
MAPI_E_UNCONFIGURED 
  
> 配置文件包含的信息不足，无法完成登录。 返回此值时，MAPI 将调用邮件存储提供程序的邮件服务入口点函数。
    
MAPI_E_USER_CANCEL 
  
> 用户通常通过单击对话框中的"取消" **按钮来取消** 操作。 
    
MAPI_E_UNKNOWN_CPID 
  
> 服务器未配置为支持客户端的代码页。
    
MAPI_E_UNKNOWN_LCID 
  
> 服务器未配置为支持客户端区域设置信息。
    
MAPI_W_ERRORS_RETURNED 
  
> 调用成功，但邮件存储提供程序提供错误信息。 返回此警告时，应成功处理呼叫。 若要测试此警告，请使用 **HR_FAILED** 宏。 有关详细信息，请参阅使用 [宏处理错误](using-macros-for-error-handling.md)。 若要从提供程序获取错误信息，请调用 [IMAPISession：：GetLastError](imapisession-getlasterror.md) 方法。 
    
## <a name="remarks"></a>备注

MAPI 调用 **IMSProvider：：Logon** 方法，以执行获取对消息存储的访问权限所需的大部分处理。 邮件存储提供程序验证访问特定存储所需的任何用户凭据，并返回 MAPI 后台处理程序和客户端应用程序可登录到  _的 lppMDB_ 参数中的邮件存储对象。 
  
除了返回的邮件存储对象用于客户端和 MAPI 后台处理程序之外，提供程序还返回 MAPI 用于控制打开的存储区的邮件存储登录对象。 邮件存储登录对象和邮件存储对象应紧密链接在邮件存储提供程序内，以便每个对象可以相互影响。 存储对象的使用和登录对象的使用应该相同;登录对象和存储对象之间应该存在一对一的对应关系，这样对象的行为就就像它们是一个公开两个接口的对象一样。 这两个对象也应该一起创建并释放在一起。 
  
MAPI 支持对象（由 MAPI 创建，在  _lpMAPISup_ 参数中传递给提供程序）提供对提供程序所需的 MAPI 中函数的访问。 这些功能包括保存和检索配置文件信息、访问通讯簿等功能。 对于  _打开的每个存储区，lpMAPISup_ 指针可能不同。 在登录后处理邮件存储的调用时，存储提供程序应该使用特定于该存储的  _lpMAPISup_ 变量。 对于打开邮件存储并成功创建邮件存储登录对象的任何登录调用，提供程序必须将指向 MAPI 支持对象的指针保存在存储登录对象中，并且必须调用[IUnknown：：AddRef](https://msdn.microsoft.com/library/ms691379%28v=VS.85%29.aspx)方法来添加对支持对象的引用。 
  
如果提供程序在登录调用期间显示对话框，则应该使用 _ulUIParam_ **参数。** 但是，如果  _ulFlags_ 包含 MDB_NO_DIALOG 标志，则不应显示对话框。 如果需要调用用户界面但  _ulFlags_ 不允许它，或者由于其他原因无法显示用户界面，则提供程序应返回MAPI_E_LOGON_FAILED。 如果 **登录** 显示一个对话框，并且用户通常通过单击对话框的"取消"按钮来取消登录，则提供程序应返回MAPI_E_USER_CANCEL。 
  
_lpEntryID_ 参数可以是 **null，** 也可以指向此邮件存储之前创建的未包装存储条目标识符。 如果  _lpEntryID_ 指向未包的条目标识符，该条目标识符可能来自多个位置之一： 
  
- 它可以是存储提供程序之前作为[PidTagEntryId](pidtagentryid-canonical-property.md) PR_ENTRYID (并写到配置文件) 标识符。
    
- 它可以是提供程序之前包装并作为[PidTagStoreEntryId](pidtagstoreentryid-canonical-property.md) PR_STORE_ENTRYID (返回给调用) 标识符。 
    
- 它可以是提供程序之前封装并作为邮件存储对象的 PR_ENTRYID 返回给调用客户端的条目标识符。 
    
在任一情况下，条目标识符可能是在不同于当前使用的计算机中创建的。
  
当  _lpEntryID_ 不 **为 null** 时，它应包含标识和查找邮件存储所需的全部信息。 此信息可能包括网络卷名称、电话号码、用户帐户名等。 如果无法使用条目标识符中的数据建立到存储的连接，则存储提供程序应显示一个对话框，允许用户选择要打开的存储区。 可能需要对话框，例如，如果服务器已重命名、帐户名称已更改或网络部分不可用。
  
当  _lpEntryID_ **为 null** 时，尚未选择使用的邮件存储。 如果提供程序支持指定存储的进一步方法，则它仍然可以在不显示对话框的情况下访问存储区。 例如，提供程序可以检查其初始化文件，也可以查找在配置时放置在其邮件服务配置文件部分的其他属性。
  
如果提供程序发现配置文件中未包含所有必需的信息，则它应返回MAPI_E_UNCONFIGURED。 然后，MAPI 将调用提供程序的邮件服务入口点函数，以使用户能够选择存储，甚至创建一个存储，并根据需要输入帐户名和密码。 MAPI 自动创建新存储的配置文件部分;此新配置文件部分可以是临时的或永久的，具体取决于其添加方式。 如果存储提供程序调用 **IMAPISupport：：ModifyProfile** 方法，则新的配置文件部分将变为永久性，并且存储将添加到 [IMAPISession：：GetMsgStoresTable](imapisession-getmsgstorestable.md) 方法返回的消息存储列表中。 
  
_lpInterface_ 参数指定新打开的存储区对象所需的接口的 IID。 在 _lpInterface_ 中传递 **null** 指定 MAPI 邮件存储接口 **IMsgStore** 是必需的。 传递邮件存储对象 IID_IMsgStore，还指定 **需要 IMsgStore。** 如果IID_IUnknown  _lpInterface_ 中传递，则提供程序应该使用从 [IUnknown](https://msdn.microsoft.com/library/ms680509%28v=VS.85%29.aspx) 派生的任何接口打开存储，这同样 (，这通常是 **IMsgStore**) 。 传递IID_IUnknown时，调用实现使用 [IUnknown：：QueryInterface](https://msdn.microsoft.com/library/ms682521%28v=VS.85%29.aspx) 方法在存储打开操作成功后选择接口。 
  
**IMSProvider：：Logon** 调用应返回足够的信息，例如存储的路径和用于访问存储的凭据，以允许 MAPI 后台处理程序登录到存储提供程序所登录的同一存储，而不显示对话框。 _lpcbSpoolSecurity_ 和 _lppbSpoolSecurity_ 参数用于返回此信息。 提供程序通过向 [MSProviderInit](msproviderinit.md) 函数的  _lpfAllocateBuffer_ 参数中的缓冲区传递指针来为此数据分配内存;提供程序将此缓冲区的大小设置在  _lpcbSpoolSecurity 中_。 
  
MAPI 在适当时释放此缓冲区。 如果 MAPI 后台处理程序对存储的登录可以单独通过配置文件部分的信息完成，则提供程序可以在  _lppbSpoolSecurity_ 中返回 null，在  _lpcbSpoolSecurity_ 中为信息大小返回 0。 MAPI 后台处理程序登录作为与存储登录不同的过程的一部分进行;由于包含传递信息的缓冲区在进程之间复制，因此它可能不在与存储提供程序进程相同的 MAPI 后台处理程序进程的相同位置的内存中。 因此，提供程序不应将地址放入此缓冲区中。 有关 MAPI 后台处理程序登录信息，请参阅 [IMSProvider：：SpoolerLogon](imsprovider-spoolerlogon.md) 方法。 
  
大多数存储提供程序使用在 _lpMAPISup_ 参数中传递的支持对象的 [IMAPISession：：OpenProfileSection](imapisession-openprofilesection.md)方法保存和检索用户凭据和选项。 **OpenProfileSection** 允许存储提供程序在配置文件部分保存其他任意信息，并将其与特定资源关联。 例如，存储提供程序可以保存与资源关联的用户帐户名称和密码以及访问该资源所需的任何路径或其他信息。 
  
属性标识符0x6600属性0x67FF提供程序可以使用的安全属性，供提供程序自行使用以在配置文件节中存储私有数据。 有关配置文件节对象中属性用法的信息，请参阅 [IProfSect ： IMAPIProp](iprofsectimapiprop.md) 方法。 
  
除了标识符为 0x6600 到 0x67FF 的属性中的任何私有数据外，存储提供程序还应在其配置文件部分提供 **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性的信息。 它应放在PR_DISPLAY_NAME的 显示名称 中— 向用户显示的标识字符串 (例如，"Microsoft 个人信息存储") ，以便用户可以区分此消息存储与可能有权访问的其他人。 **PR_DISPLAY_NAME** 通常包含服务器名称、用户帐户名或路径。 
  
某些配置文件节属性在邮件存储表中可见;其他在 MAPI 子系统的安装、安装和配置过程中可见。 通常，提供程序会为新的配置文件节提供这些可见属性的信息，这不包括保存的凭据或私人信息，以及发现属性信息已更改时。 有关配置文件部分详细信息，请参阅 [IMAPISupport：：OpenProfileSection](imapisupport-openprofilesection.md)。
  
成功登录用户后，在返回到 MAPI 之前，存储提供程序应为资源的状态行创建属性数组并调用 [IMAPISupport：：ModifyStatusRow](imapisupport-modifystatusrow.md) 方法。 
  
 **打开** 为当前 MAPI 会话打开的邮件存储的登录调用将跳过之前描述的很多处理。 这些调用不会创建状态行、返回邮件存储登录对象、调用 MAPI 支持对象的 **AddRef** 或返回 MAPI 后台处理程序登录的数据。 这些调用会返回S_OK请求的接口返回消息存储对象。 
  
若要检测此类调用，提供程序应维护已为此提供程序对象打开的存储区的邮件存储提供程序对象中的列表。 处理 **登录调用** 时，提供程序应扫描此打开的存储区列表，并确定要登录到的存储区是否已打开。 如果是，则不需要检查用户凭据，如果可能，应避免显示对话框。 如果必须显示对话框，提供程序应检查返回的信息，以查看是否已再次打开存储区。 此外，提供程序应在登录呼叫处理开始时使用  _lpEntryID_ 检查 **重复** 的打开。 
  
访问打开的 **存储区** 的登录调用的标准处理如下： 
  
1. 如果请求的新接口与现有存储的接口相同，则存储提供程序将调用现有存储对象的 **AddRef。** 否则，它将调用 **QueryInterface** 获取新接口。 如果存储不支持新接口，提供程序应返回错误值MAPI_E_INTERFACE_NOT_SUPPORTED。 
    
2. 提供程序返回一个指针，指向  _lppMDB_ 中现有存储对象的必需接口。
    
3. 提供程序在 _lppMSLogon 中返回 null。_
    
4. 提供程序不应打开调用中传递的支持对象的配置文件。 此外，它不应注册提供程序唯一标识符、注册状态行或返回 MAPI 后台处理程序登录数据。
    
5. 提供程序不应为 **支持对象调用 AddRef，** 因为它不需要指向该对象的指针。 
    
只要有可能，提供程序应为 **登录** 调用返回相应的错误和警告字符串，因为这样做可大大减轻用户在确定某些内容不起作用的原因时的负担。 若要返回这些字符串，提供程序将设置 **MAPIERROR** 结构中的成员。 如果 MAPI 由提供程序返回，则查找、使用并释放 **MAPIERROR** 结构。 
  
此 **MAPIERROR** 结构的内存应通过使用 **在 MSProviderInit** 调用上 _传入 lpfAllocateBuffer_ 的缓冲区进行分配。 如果在 **Logon** _ulFlags_ 中设置了 MAPI_UNICODE，则返回的结构中包含的任何错误字符串都应采用 Unicode 格式;否则，它们应位于 ANSI 字符集。 
  
对于从 **Logon** 返回的多数错误值，MAPI 将禁用失败提供程序所属的邮件服务。 MAPI 在 MAPI 会话的生命周期内不会调用属于这些服务的任何提供程序。 相反，当 **登录** 从MAPI_E_FAILONEPROVIDER返回错误值时，MAPI 不会禁用提供程序所属的邮件服务。 **如果** 登录MAPI_E_FAILONEPROVIDER如果遇到一个错误，而该错误不保证在会话的整个生命周期内禁用整个服务，则应该返回此状态。 例如，如果提供程序不允许显示用户界面并且所需的密码不可用，则提供程序可能会返回此错误。 
  
如果提供程序从MAPI_E_UNCONFIGURED返回消息，MAPI 将调用提供程序的邮件服务条目函数，然后重试登录。 MAPI 将MSG_SERVICE_CONFIGURE作为上下文传递，为服务提供自行配置的机会。 如果客户端已选择允许在登录时使用用户界面，该服务可以显示其配置属性表以便用户输入配置信息。
  
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

