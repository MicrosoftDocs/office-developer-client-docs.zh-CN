---
title: 获取存储的全局地址列表或一组地址列表
TOCTitle: Get the Global Address List or a set of address lists for a store
ms:assetid: a361ac58-25c6-4ce1-97b0-403ad67ee7a4
ms:mtpsurl: https://docs.microsoft.com/office/client-developer/outlook/pia/how-to-get-the-global-address-list-or-a-set-of-address-lists-for-a-store
ms:contentKeyID: 55119800
ms.date: 12/03/2019
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 7f0f7ba9b8854603646dc41e1017c2465c4af2d8
ms.sourcegitcommit: 37080eb0087261320e24e6f067e5f434a812b2d2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/04/2019
ms.locfileid: "39819327"
---
# <a name="get-the-global-address-list-or-a-set-of-address-lists-for-a-store"></a>获取存储的全局地址列表或一组地址列表

本主题包含两个代码示例，它们演示如何获取与存储相关的全局地址列表 (GAL)，以及如何获取与存储相关的所有地址列表。

## <a name="example"></a>示例

在配置文件中定义了多个 Exchange 帐户的 Outlook 会话中，可以有多个与存储关联的地址列表。 在下面的各个代码示例中，受关注的特定存储是活动的资源管理器中显示的当前文件夹的存储，但用于获取全局地址列表或存储的一组 [AddressList](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook.addresslist?redirectedfrom=MSDN&view=outlook-pia) 对象的算法适用于任何 Exchange 存储。

第一个代码示例包含 DisplayGlobalAddressListForStore 方法和 GetGlobalAddressList 函数。 DisplayGlobalAddressListForStore 方法会在“**选择姓名**”对话框中显示与当前存储相关联的全局地址列表。 DisplayGlobalAddressListForStore 会首先获取当前存储。 如果当前存储是 Exchange 存储，系统会调用 GetGlobalAddressList 以获得与当前存储关联的全局地址列表。 

GetGlobalAddressList 会使用 [PropertyAccessor](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook.propertyaccessor?redirectedfrom=MSDN&view=outlook-pia) 对象和 MAPI 属性 https://schemas.microsoft.com/mapi/proptag/0x3D150102 来获取地址列表和当前存储的 PR\_EMSMDB\_SECTION\_UID 属性。 如果它们的 PR\_EMSMDB\_SECTION\_UID 属性匹配，那么 GetGlobalAddressList 会将地址列表识别为与存储关联，而且如果地址列表的 [AddressListType](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook.addresslist.addresslisttype?redirectedfrom=MSDN&view=outlook-pia#Microsoft_Office_Interop_Outlook_AddressList_AddressListType) 属性是 [olExchangeGlobalAddressList](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook.oladdresslisttype?redirectedfrom=MSDN&view=outlook-pia)，那么地址列表便是全局地址列表。 如果 GetGlobalAddressList 调用成功，DisplayGlobalAddressListForStore 将使用 [SelectNamesDialog] (对象在"选择姓名"对话框中显示返回的全局地址 https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook.selectnamesdialog?redirectedfrom=MSDN&view=outlook-pia\) 列表。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。 下面的代码行展示了如何在 C\# 中执行导入和分配操作。

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```

```csharp
void DisplayGlobalAddressListForStore()
{
    Outlook.Folder currentFolder =
        Application.ActiveExplorer().CurrentFolder
        as Outlook.Folder;
    Outlook.Store currentStore = currentFolder.Store;
    if (currentStore.ExchangeStoreType !=
        Outlook.OlExchangeStoreType.olNotExchange)
    {
        Outlook.SelectNamesDialog snd = 
            Application.Session.GetSelectNamesDialog();
        Outlook.AddressList addrList = 
            GetGlobalAddressList(currentStore);
        if (addrList != null)
        {
            snd.InitialAddressList = addrList;
            snd.Display();
        }
    }
}

public Outlook.AddressList GetGlobalAddressList(Outlook.Store store)
{
    string  PR_EMSMDB_SECTION_UID = 
        @"http://schemas.microsoft.com/mapi/proptag/0x3D150102";
    if (store == null)
    {
        throw new ArgumentNullException();
    }
    Outlook.PropertyAccessor oPAStore = store.PropertyAccessor;
    string storeUID = oPAStore.BinaryToString(
        oPAStore.GetProperty(PR_EMSMDB_SECTION_UID));
    foreach (Outlook.AddressList addrList 
        in Application.Session.AddressLists)
    {
        Outlook.PropertyAccessor oPAAddrList = 
            addrList.PropertyAccessor;
        string addrListUID = oPAAddrList.BinaryToString(
            oPAAddrList.GetProperty(PR_EMSMDB_SECTION_UID));
        // Return addrList if match on storeUID
        // and type is olExchangeGlobalAddressList.
        if (addrListUID == storeUID && addrList.AddressListType ==
            Outlook.OlAddressListType.olExchangeGlobalAddressList)
        {
            return addrList;
        }
    }
    return null;
}
```

第二个代码示例包含 EnumerateAddressListsForStore 方法和 GetAddressLists 函数。 EnumerateAddressListsForStore 方法会显示为当前存储定义的每个地址列表的类型和解析顺序。 EnumerateAddressListsForStore 会首先获取当前存储，然后调用 GetAddressLists 来获取包含当前存储的 AddressList 对象的 .NET Framework 泛型 [List\<T\>](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1?redirectedfrom=MSDN&view=netframework-4.8) 对象。 

GetAddressLists 会枚举为会话定义的各地址列表，使用 PropertyAccessor 对象和 MAPI 命名属性 https://schemas.microsoft.com/mapi/proptag/0x3D150102 来获取地址列表的 PR\_EMSMDB\_SECTION\_UID 属性和当前存储的 PR\_EMSMDB\_SECTION\_UID 属性。 如果它们的 PR\_EMSMDB\_SECTION\_UID 属性互相匹配，则 GetGlobalAddressList 会将地址列表识别为与存储关联，并返回当前存储的一组地址列表。 然后， EnumerateAddressListsForStore 会使用 **AddressList** 对象的 [AddressListType](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook.addresslist.addresslisttype?redirectedfrom=MSDN&view=outlook-pia#Microsoft_Office_Interop_Outlook_AddressList_AddressListType) 和 [ResolutionOrder](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook.addresslist.resolutionorder?redirectedfrom=MSDN&view=outlook-pia#Microsoft_Office_Interop_Outlook_AddressList_ResolutionOrder) 属性来显示返回的每个地址列表的类型和解析顺序。


```csharp
private void EnumerateAddressListsForStore()
{
    Outlook.Folder currentFolder =
        Application.ActiveExplorer().CurrentFolder
        as Outlook.Folder;
    Outlook.Store currentStore = currentFolder.Store;
    List<Outlook.AddressList> addrListsForStore = 
        GetAddressLists(currentStore);
    foreach (Outlook.AddressList addrList in addrListsForStore)
    {
        Debug.WriteLine(addrList.Name 
            + " " + addrList.AddressListType.ToString()
            + " Resolution Order: " +
            addrList.ResolutionOrder);
    }
}
public List<Outlook.AddressList> GetAddressLists(Outlook.Store store)
{
    List<Outlook.AddressList> addrLists = 
        new List<Microsoft.Office.Interop.Outlook.AddressList>();
    string PR_EMSMDB_SECTION_UID =
        @"http://schemas.microsoft.com/mapi/proptag/0x3D150102";
    if (store == null)
    {
        throw new ArgumentNullException();
    }
    Outlook.PropertyAccessor oPAStore = store.PropertyAccessor;
    string storeUID = oPAStore.BinaryToString(
        oPAStore.GetProperty(PR_EMSMDB_SECTION_UID));
    foreach (Outlook.AddressList addrList
        in Application.Session.AddressLists)
    {
        Outlook.PropertyAccessor oPAAddrList =
            addrList.PropertyAccessor;
        string addrListUID = oPAAddrList.BinaryToString(
            oPAAddrList.GetProperty(PR_EMSMDB_SECTION_UID));
        // Return addrList if match on storeUID
        // and type is olExchangeGlobalAddressList.
        if (addrListUID == storeUID)
        {
            addrLists.Add(addrList);
        }
    }
    return addrLists;
}
```

## <a name="see-also"></a>另请参阅

- [通讯簿](address-book.md)

