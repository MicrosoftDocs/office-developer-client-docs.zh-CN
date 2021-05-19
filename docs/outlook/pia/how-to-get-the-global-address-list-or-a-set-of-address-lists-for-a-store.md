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
# <a name="get-the-global-address-list-or-a-set-of-address-lists-for-a-store"></a><span data-ttu-id="2ef52-102">获取存储的全局地址列表或一组地址列表</span><span class="sxs-lookup"><span data-stu-id="2ef52-102">Get the Global Address List or a set of address lists for a store</span></span>

<span data-ttu-id="2ef52-103">本主题包含两个代码示例，它们演示如何获取与存储相关的全局地址列表 (GAL)，以及如何获取与存储相关的所有地址列表。</span><span class="sxs-lookup"><span data-stu-id="2ef52-103">This topic contains two code examples that show how to get the Global Address List (GAL) that is associated with a store, and how to get all of the address lists that are associated with a store.</span></span>

## <a name="example"></a><span data-ttu-id="2ef52-104">示例</span><span class="sxs-lookup"><span data-stu-id="2ef52-104">Example</span></span>

<span data-ttu-id="2ef52-105">在配置文件中定义了多个 Exchange 帐户的 Outlook 会话中，可以有多个与存储关联的地址列表。</span><span class="sxs-lookup"><span data-stu-id="2ef52-105">In an Outlook session where multiple Exchange accounts are defined in the profile, there can be multiple address lists associated with a store.</span></span> <span data-ttu-id="2ef52-106">在下面的各个代码示例中，受关注的特定存储是活动的资源管理器中显示的当前文件夹的存储，但用于获取全局地址列表或存储的一组 [AddressList](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook.addresslist?redirectedfrom=MSDN&view=outlook-pia) 对象的算法适用于任何 Exchange 存储。</span><span class="sxs-lookup"><span data-stu-id="2ef52-106">In each of the following code examples, the specific store of interest is the store for the current folder displayed in the active explorer, but the algorithm to get a Global Address List or a set of [AddressList](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook.addresslist?redirectedfrom=MSDN&view=outlook-pia) objects for a store applies to any Exchange store.</span></span>

<span data-ttu-id="2ef52-107">第一个代码示例包含 DisplayGlobalAddressListForStore 方法和 GetGlobalAddressList 函数。</span><span class="sxs-lookup"><span data-stu-id="2ef52-107">The first code example contains the DisplayGlobalAddressListForStore method and the GetGlobalAddressList function.</span></span> <span data-ttu-id="2ef52-108">DisplayGlobalAddressListForStore 方法会在“**选择姓名**”对话框中显示与当前存储相关联的全局地址列表。</span><span class="sxs-lookup"><span data-stu-id="2ef52-108">The DisplayGlobalAddressListForStore method displays, in the **Select Names** dialog box, the Global Address List that is associated with the current store.</span></span> <span data-ttu-id="2ef52-109">DisplayGlobalAddressListForStore 会首先获取当前存储。</span><span class="sxs-lookup"><span data-stu-id="2ef52-109">DisplayGlobalAddressListForStore first obtains the current store.</span></span> <span data-ttu-id="2ef52-110">如果当前存储是 Exchange 存储，系统会调用 GetGlobalAddressList 以获得与当前存储关联的全局地址列表。</span><span class="sxs-lookup"><span data-stu-id="2ef52-110">If the current store is an Exchange store, GetGlobalAddressList is called to obtain the Global Address List associated with the current store.</span></span> 

<span data-ttu-id="2ef52-111">GetGlobalAddressList 会使用 [PropertyAccessor](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook.propertyaccessor?redirectedfrom=MSDN&view=outlook-pia) 对象和 MAPI 属性 https://schemas.microsoft.com/mapi/proptag/0x3D150102 来获取地址列表和当前存储的 PR\_EMSMDB\_SECTION\_UID 属性。</span><span class="sxs-lookup"><span data-stu-id="2ef52-111">GetGlobalAddressList uses the [PropertyAccessor](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook.propertyaccessor?redirectedfrom=MSDN&view=outlook-pia) object and the MAPI property https://schemas.microsoft.com/mapi/proptag/0x3D150102 to obtain the PR\_EMSMDB\_SECTION\_UID property of an address list and the current store.</span></span> <span data-ttu-id="2ef52-112">如果它们的 PR\_EMSMDB\_SECTION\_UID 属性匹配，那么 GetGlobalAddressList 会将地址列表识别为与存储关联，而且如果地址列表的 [AddressListType](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook.addresslist.addresslisttype?redirectedfrom=MSDN&view=outlook-pia#Microsoft_Office_Interop_Outlook_AddressList_AddressListType) 属性是 [olExchangeGlobalAddressList](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook.oladdresslisttype?redirectedfrom=MSDN&view=outlook-pia)，那么地址列表便是全局地址列表。</span><span class="sxs-lookup"><span data-stu-id="2ef52-112">GetGlobalAddressList identifies an address list as associated with a store if their PR\_EMSMDB\_SECTION\_UID properties match, and the address list is the Global Address List if its [AddressListType](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook.addresslist.addresslisttype?redirectedfrom=MSDN&view=outlook-pia#Microsoft_Office_Interop_Outlook_AddressList_AddressListType) property is [olExchangeGlobalAddressList](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook.oladdresslisttype?redirectedfrom=MSDN&view=outlook-pia).</span></span> <span data-ttu-id="2ef52-113">如果 GetGlobalAddressList 调用成功，DisplayGlobalAddressListForStore 将使用 [SelectNamesDialog] (对象在"选择姓名"对话框中显示返回的全局地址 https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook.selectnamesdialog?redirectedfrom=MSDN&view=outlook-pia\) 列表。</span><span class="sxs-lookup"><span data-stu-id="2ef52-113">If the call to GetGlobalAddressList succeeds, DisplayGlobalAddressListForStore uses the [SelectNamesDialog](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook.selectnamesdialog?redirectedfrom=MSDN&view=outlook-pia\) object to display the returned Global Address List in the **Select Names** dialog box.</span></span>

<span data-ttu-id="2ef52-114">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="2ef52-114">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the Outlook variable when you import the **Microsoft.Office.Interop.Outlook** namespace.</span></span> <span data-ttu-id="2ef52-115">不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="2ef52-115">The **using** statement must not occur directly before the functions in the code example but must be added before the public Class declaration.</span></span> <span data-ttu-id="2ef52-116">下面的代码行展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="2ef52-116">The following line of code shows how to do the import and assignment in C\#.</span></span>

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

<span data-ttu-id="2ef52-117">第二个代码示例包含 EnumerateAddressListsForStore 方法和 GetAddressLists 函数。</span><span class="sxs-lookup"><span data-stu-id="2ef52-117">The second code example contains the EnumerateAddressListsForStore method and GetAddressLists function.</span></span> <span data-ttu-id="2ef52-118">EnumerateAddressListsForStore 方法会显示为当前存储定义的每个地址列表的类型和解析顺序。</span><span class="sxs-lookup"><span data-stu-id="2ef52-118">The EnumerateAddressListsForStore method displays the type and resolution order of each address list defined for the current store.</span></span> <span data-ttu-id="2ef52-119">EnumerateAddressListsForStore 会首先获取当前存储，然后调用 GetAddressLists 来获取包含当前存储的 AddressList 对象的 .NET Framework 泛型 [List\<T\>](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1?redirectedfrom=MSDN&view=netframework-4.8) 对象。</span><span class="sxs-lookup"><span data-stu-id="2ef52-119">EnumerateAddressListsForStore first obtains the current store, and then calls GetAddressLists to obtain a .NET Framework generic [List\<T\>](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1?redirectedfrom=MSDN&view=netframework-4.8) object that contains AddressList objects for the current store.</span></span> 

<span data-ttu-id="2ef52-120">GetAddressLists 会枚举为会话定义的各地址列表，使用 PropertyAccessor 对象和 MAPI 命名属性 https://schemas.microsoft.com/mapi/proptag/0x3D150102 来获取地址列表的 PR\_EMSMDB\_SECTION\_UID 属性和当前存储的 PR\_EMSMDB\_SECTION\_UID 属性。</span><span class="sxs-lookup"><span data-stu-id="2ef52-120">GetAddressLists enumerates each address list defined for the session, uses the PropertyAccessor object and the MAPI named property https://schemas.microsoft.com/mapi/proptag/0x3D150102 to obtain the PR\_EMSMDB\_SECTION\_UID property of an address list, and the PR\_EMSMDB\_SECTION\_UID property of a current store.</span></span> <span data-ttu-id="2ef52-121">如果它们的 PR\_EMSMDB\_SECTION\_UID 属性互相匹配，则 GetGlobalAddressList 会将地址列表识别为与存储关联，并返回当前存储的一组地址列表。</span><span class="sxs-lookup"><span data-stu-id="2ef52-121">GetGlobalAddressList identifies an address list as associated with a store if their PR\_EMSMDB\_SECTION\_UID properties match, and returns a set of address lists for the current store.</span></span> <span data-ttu-id="2ef52-122">然后， EnumerateAddressListsForStore 会使用 **AddressList** 对象的 [AddressListType](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook.addresslist.addresslisttype?redirectedfrom=MSDN&view=outlook-pia#Microsoft_Office_Interop_Outlook_AddressList_AddressListType) 和 [ResolutionOrder](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook.addresslist.resolutionorder?redirectedfrom=MSDN&view=outlook-pia#Microsoft_Office_Interop_Outlook_AddressList_ResolutionOrder) 属性来显示返回的每个地址列表的类型和解析顺序。</span><span class="sxs-lookup"><span data-stu-id="2ef52-122">EnumerateAddressListsForStore then uses the [AddressListType](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook.addresslist.addresslisttype?redirectedfrom=MSDN&view=outlook-pia#Microsoft_Office_Interop_Outlook_AddressList_AddressListType) and [ResolutionOrder](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook.addresslist.resolutionorder?redirectedfrom=MSDN&view=outlook-pia#Microsoft_Office_Interop_Outlook_AddressList_ResolutionOrder) properties of the **AddressList** object to display the type and resolution order for each returned address list.</span></span>


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

## <a name="see-also"></a><span data-ttu-id="2ef52-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2ef52-123">See also</span></span>

- [<span data-ttu-id="2ef52-124">通讯簿</span><span class="sxs-lookup"><span data-stu-id="2ef52-124">Address book</span></span>](address-book.md)

