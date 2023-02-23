**IMPORTANT:** All tables are FullyAuditedEntity and TrackEntityHistory

NOTE:

- Namespace:
    - Vhs.Bms.Common
    - Vhs.Bms.Main
    - Vhs.Bms.Accounting
    - Vhs.Bms.Operation
    - Vhs.Bms.Report
    - Vhs.Bms.Integration

# I. Enum

## ServiceType

| Type | Value |
| --- | --- |
| Management | 1   |
| Parking | 2   |
| Water | 3   |

## PaymentMethod

| Types | Value |
| --- | --- |
| Cash | 1   |
| WireTransfer | 2   |

## Gender

| Types | Values |
| --- | --- |
| Other | 1   |
| Male | 2   |
| Female | 3   |

## ResidentRequestStatus

| Types | Values |
| --- | --- |
| Initial | 0   |
| Submitted | 1   |
| Approved | 2   |
| Rejected | -1   |

# II. Structure

## ManagementFeeType

### Example

| OrderIndex | Code | Name |
| --- | --- | --- |
| 1   | CD  | Cư Dân |
| 2   | TM  | Thương Mại |

### Description

| Field | Type | Details | Required |
| --- | --- | --- | --- |
| OrderIndex | Int |     | X   |
| Code | String | Length:10 | X   |
| Name | String | Length:30 | X   |

## ManagementFeeConfig

### Example

| OrderIndex | FeeTypeId | Level | Min | Max | Fee | EffectiveDate | ExpirationDate | ExtraFee | VAT |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 1   | CD  | 1   | 1   | 9999 | 5,000 | 20/01/2019 | 20/02/2020 |     |     |
| 2   | TM  | 1   | 1   | 9999 | 10,000 | 30/01/2020 | 30/01/2025 |     |     |

### Description

| Field | Type | Details | Required | Note |
| --- | --- | --- | --- | --- |
| OrderIndex | Int |     | X   |     |
| Level | Int |     | X   |     |
| Min | Decimal |     | X   |     |
| Max | Decimal |     | X   |     |
| Fee | Decimal |     | X   |     |
| EffectiveDate | DateTime |     | X   | Begin of Day |
| ExpirationDate | DateTime |     |     | End of Day |
| ExtraFee | Decimal |     |     |     |
| VAT | Decimal |     |     |     |
| FeeTypeId | Int | Navigate to ManagementFeeTypeId | X   |     |

## WaterFeeType

### Example

| OrderIndex | Code | Name |
| --- | --- | --- |
| 1   | SH  | Sinh Hoạt |
| 2   | SX  | Sản Xuất |

### Description

| Field | Type | Details | Required |
| --- | --- | --- | --- |
| OrderIndex | Int |     | X   |
| Code | String | Length:10 | X   |
| Name | String | Length:30 | X   |

## WaterFeeConfig

### Example

| OrderIndex | FeeTypeId | Level | Min | Max | Fee | EffectiveDate | ExpirationDate | ExtraFee | VAT |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 1   | SH  | 1   | 1   | 10  | 5,000 | 20/01/2019 | 20/02/2020 |     |     |
| 2   | SH  | 2   | 11  | 20  | 8,000 | 20/01/2019 | 20/02/2020 |     |     |
| 3   | SX  | 1   | 1   | 9999 | 10,000 | 30/01/2020 | 30/01/2025 |     |     |

### Description

| Field | Type | Details | Required | Note |
| --- | --- | --- | --- | --- |
| OrderIndex | Int |     | X   |     |
| Level | Int |     | X   |     |
| Min | Decimal |     | X   |     |
| Max | Decimal |     | X   |     |
| Fee | Decimal |     | X   |     |
| EffectiveDate | DateTime |     | X   | Begin of Day |
| ExpirationDate | DateTime |     |     | End of Day |
| ExtraFee | Decimal |     |     |     |
| VAT | Decimal |     |     |     |
| FeeTypeId | Int | Navigate to WaterFeeType | X   |     |

## ParkingFeeType

### Example

| OrderIndex | Code | Name |
| --- | --- | --- |
| 1   | XM1 | Phí Xe Máy 1 |
| 2   | OTO1 | Phí Ô tô 1 |
| 3   | OTO2 | Phí Ô tô 2 |

### Description

| Field | Type | Details | Required |
| --- | --- | --- | --- |
| OrderIndex | Int |     | X   |
| Code | String | Length:10 | X   |
| Name | String | Length:20 | X   |

## ParkingFeeConfig

### Example

| OrderIndex | FeeTypeId | Level | Min | Max | Fee | EffectiveDate | ExpirationDate | ExtraFee | VAT |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 1   | XM1 | 1   | 1   | 2   | 50,000 | 20/01/2019 | 20/02/2020 |     |     |
| 2   | XM2 | 2   | 2   | 9999 | 80,000 | 20/01/2019 | 20/02/2020 |     |     |
| 3   | OTO1 | 1   | 1   | 9999 | 1000,000 | 30/01/2020 | 30/01/2025 |     |     |

### Description

| Field | Type | Details | Required | Note |
| --- | --- | --- | --- | --- |
| OrderIndex | Int |     | X   |     |
| Level | Int |     | X   |     |
| Min | Decimal |     | X   |     |
| Max | Decimal |     | X   |     |
| Fee | Decimal |     | X   |     |
| EffectiveDate | DateTime |     | X   | Begin of Day |
| ExpirationDate | DateTime |     |     | End of Day |
| ExtraFee | Decimal |     |     |     |
| VAT | Decimal |     |     |     |
| FeeTypeId | Int | Navigate to ParkingFeeType | X   |     |

## VehicleType

### Example

| OrderIndex | Code | Name |
| --- | --- | --- |
| 1   | XM  | Xe Máy |
| 2   | OTO | Ô tô |

### Description

| Field | Type | Details | Required |
| --- | --- | --- | --- |
| OrderIndex | Int |     | X   |
| Code | String | Length:10 | X   |
| Name | String | Length:30 | X   |

## ParkingZones

### Example

| OrderIndex | Code | Name |
| --- | --- | --- |
| 1   | HAM | Hầm |
| 2   | 345 | Tầng 345 |

### Description

| Field | Type | Details | Required |
| --- | --- | --- | --- |
| OrderIndex | Int |     | X   |
| Code | String | Length:10 | X   |
| Name | String | Length:30 | X   |

## ResidentRelationshipType

### Example

| OrderIndex | Code | Name |
| --- | --- | --- |
| 1   | CSH | Chủ Sở Hữu |
| 2   | KT  | Khách Thuê |
| 3   | NT  | Người Thân |

### Description

| Field | Type | Details | Required |
| --- | --- | --- | --- |
| OrderIndex | Int |     | X   |
| Code | String | Length:10 | X   |
| Name | String | Length:30 | X   |

## RequestType

### Example

| OrderIndex | Code | Name |
| --- | --- | --- |
| 1   | CM  | Cấp Mới |
| 2   | CL  | Cấp Lại |

### Description

| Field | Type | Details | Required |
| --- | --- | --- | --- |
| OrderIndex | Int |     | X   |
| Code | String | Length:10 | X   |
| Name | String | Length:30 | X   |

## CardIssueFeeType

### Example

| OrderIndex | Code | Name | Fee |
| --- | --- | --- | --- |
| 1   | HTE | Từ Thẻ H sang Thẻ E | 0 |
| 2   | HTH | Thẻ H sang Thẻ H | 0 |
| 3   | MPALL | Miễn Phí Tất Cả | 0 |

### Description

| Field | Type | Details | Required |
| --- | --- | --- | --- |
| OrderIndex | Int |     | X   |
| Code | String | Length:10 | X   |
| Name | String | Length:30 | X   |
| Fee | Decimal |  | X   |

## Blocks

### Example:

| OrderIndex | Code | Name |
| --- | --- | --- |
| 1   | CT1 | Tòa CT1 |
| 2   | CT2 | Tòa CT2 |

### Description

| Field | Type | Details | Required |
| --- | --- | --- | --- |
| OrderIndex | Int |     | X   |
| Code | String | Length: 10 | X   |
| Name | String | Length: 30 | X   |

## Apartment

### Example:

| OrderIndex | Code | Name | Built-up area | Carpet Area | Hand-over Date | ManagementFeeTypeId | BlockId | WaterFeeTypeId |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 1   | CT1.1001 | CT1.1001 | 120 | 100 | 01/01/1979 | Cư Dân | CT1 | Sinh Hoạt |
| 2   | CT1.1002 | CT1.1002 | 55  | 40  | 02/02/2020 | Thương Mại | CT1 | Văn Phòng |

### Description:

| Field | Type | Details | Required | Note |
| --- | --- | --- | --- | --- |
| OrderIndex | Int |     | X   |     |
| Code | String | Length: 30 | X   |     |
| Name | String | Length: 30 | X   |     |
| BuiltUpArea | Decimal |     |     |     |
| CarpetArea | Decimal |     | X   |     |
| HandOverDate | DateTime |     |     |     |
| ManagementFeeTypeId | Int | Navigate to ManagementFeeTypeId (dropdown) |     | Required when have HandoverDate |
| BlockId | Int | Navigate to BlockId (dropdown) | X   |     |
| WaterFeeTypeId | Int | Navigate to WaterFeeTypeId (dropdown) |     | Required when have HandoverDate |

## Card

### Example:

| PrintedCode | Code1 | Code2 | IsBroken | IsLost |
| --- | --- | --- | --- | --- |
| E03524 | 3285635350 | 0300138265 | Yes | No  |
| E00496 | 2454487787 | 0848656100 | No  | No  |

### Description:

| Field | Type | Details | Required | Note |
| --- | --- | --- | --- | --- |
| PrintedCode | String | Length: 10 | X   |     |
| Code1 | String | Length: 12 |     |     |
| Code2 | String | Length: 12 |     |     |
| IsBroken | Boolean | Y/N |     | Default: N |
| IsLost | Boolean | Y/N |     | Default: N |

## Vehicle

### Example:

| Apartment | LicensePlate | VehicleTypeId | Name | Owner | PhoneNumber | RegistrationDate | ExpirationDate | CanceledDate | LockDate | CardId | ParkingZoneId | ParkingFeeTypeId |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| CT2.802 | 29K18993 | Ô tô | HonDa Civic | Luong Tien Dat | 0912637882 | 10/11/2010 | 10/3/2011 |     | 15/5/2011 | E03524 | Hầm | Ô tô |
| CT3.910 | 29D28475 | Xe máy | Z1000 | Luong Tien Dat |     | 15/11/2020 |     | 30/12/2020 |     | E00496 | Tầng 345 | Xe máy |

### Description:

| Field | Type | Details | Required | Note |
| --- | --- | --- | --- | --- |
| LicensePlate | String | Length: 50 | X   |     |
| Name | String | Length: 50 | X   |     |
| Owner | String | Length: 100 | X   |     |
| PhoneNumber | String | Length: 30 |     |     |
| RegistrationDate | DateTime |     | X   |     |
| ExpirationDate | DateTime |     |     |     |
| CanceledDate | DateTime |     |     |     |
| LockDate | DateTime |     |     | Ví dụ: 10 ngày kể từ kỳ thanh toán tự lock |
| Apartment | Int | Navigate to  ApartmentId (p-dropdown) | X   |     |
| VehicleTypeId | Int | Navigate to VehicleTypeId (dropdown) | X   |     |
| CardId | Int | Navigate to CardId (p-dropdown) | X   |     |
| ParkingZoneId | Int | Navigate to ParkingZoneId (dropdown) | X   |     |
| ParkingFeeTypeId | Int | Navigate to ParkingFeeTypeId (dropdown) | X   |     |

## Resident

### Example:

| ApartmentId | FullName | PhoneNumber | Email | IdNumber | ResidentRelationshipTypeId | Gender | DateOfBirth | Address | Card |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| CT1.701 | Luong Tien Dat | 01234567899 | [tiendat@gmail.com](mailto:tiendat@gmail.com) |     | Chủ sở hữu | Nam | 29/2/1997 | Long Bien - Ha Noi | E03524 |
| CT2.802 | Luong Van Ba |     | [vanba@gmail.com](mailto:vanba@gmail.com) | 12345672 |     | Nam |     | Hồ Chí Minh |     |
| CT3.910 | Luong Thi Linh | 05719203892 |     | 76523444 | Người thân | Nữ  | 29/2/2005 |     | E00496 |

### Description:

| Field | Type | Details | Required | Note |
| --- | --- | --- | --- | --- |
| FullName | String | Length: 100 | X   |     |
| PhoneNumber | String | Length: 30 |     |     |
| Email | String | Length: 50 |     |     |
| IdNumber | String | Length: 20 |     |     |
| Gender | Enum |     |     | Default: 1 |
| DateOfBirth | DateTime |     |     |     |
| Address | String | Length: 300 |     |     |
| ApartmentId | Int | Navigate to ApartmentId (p-dropdown) | X   |     |
| CardId | Int | Navigate to CardId (p-dropdown) |     |     |
| ResidentRelationshipTypeId | Int | Navigate to ResidentRelationshipTypeId (dropdown) |     |     |

## WaterUsage

### Example:

| ApartmentId | FromDate | ToDate | PreValue | Value | GrandTotal | Details |
| --- | --- | --- | --- | --- | --- | --- |
| CT1.1001 | 26/11/2020 | 26/12/2020 | 0   | 35  | 55,000 |     |
| CT1.701 | 26/11/2020 | 26/12/2020 | 12  | 45  | 62,000 |     |

### Description

| Field | Type | Details | Required | Note |
| --- | --- | --- | --- | --- |
| FromDate | DateTime |     | X   |     |
| ToDate | DateTime |     | X   |     |
| PreValue | Decimal |     | X   |     |
| Value | Decimal |     | X   |     |
| GrandTotal | Decimal |     |     |     |
| Details | String | Length: 800 |     |     |
| ApartmentId | Int | Navigate to ApartmentId | X   |     |

## AccountingBalance

### Example:

| ApartmentId | ServiceType | ObjType | Paymentmethod | Description | BillingPeriod | FromDate | ToDate | ChargeAmount | PaidAmount | PrevBalance | CurrentBalance | IsPaid |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| CT1.1001 | ManagementFee | CD  | Cash |     |11/2020| 26/11/2020 | 26/12/2020 | 50,000 | 35,000 | 55,000 | 70,000 |     |
| CT1.701 | WaterFee | SX  | WireTransfer |     |11/2020| 26/11/2020 | 26/12/2020 | 12,000 | 45,000 | 62,000 | 29,000 |     |

### Description

| Field | Type | Details | Required | Note |
| --- | --- | --- | --- | --- |
| ServiceType | Enum |     | X   |     |
| ObjType | Int | Navigate to ManagementFeeType/WaterFeeType/VehicleFeeType | X   |     |
| Paymentmethod | Enum |     |    |     |
| Description |String | LicensePlate/WaterUsage |     |     |
| BillingPeriod | DateTime |     | X   |     |
| FromDate | DateTime |     | X   |     |
| ToDate | DateTime |     | X   |     |
| ChargeAmount | Decimal |     |     |     |
| PaidAmount | Decimal |     |     |     |
| PrevBalance | Decimal |     |     |     |
| CurrentBalance | Decimal |     |     |     |
| IsPaid | Boolean | Y/N | Default: N |     |
| ApartmentId | Int | Navigate to ApartmentId | X   |     |
| VehicleId | Int | Navigate to VehicleId | X   |     |

## ResidentRequest

### Example

| Requester | PhoneNumber | AuditTime | RequestStatus | ApartmentId | AuditUser | ResidentRelationshipTypeId | RequestTypeId | Note |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Andrew | 0123456789 | 31/01/1998 | Approved | CT1.1001 | Phạm Hương | Chủ Sở Hữu | Cấp Lại |     |
| Rachel | 9876543210 | 31/01/1998 | Rejected | CT1.701 | Phạm Hương | Khách Thuê | Cấp Mới | Từ Chối |

### Description

| Field | Type | Details | Required |
| --- | --- | --- | --- |
| Requester | String | Length:100 | X   |
| PhoneNumber | String | Length:30 |     |
| AuditTime | String | Length:30 |     |
| Note |     |     |     |
| RequestStatus | Enum |     | X   |
| AuditUser | Int | Navitgate to UserId |     |
| ApartmentId | Int | Navigate to ApartmentId | X   |
| ResidentRelationshipTypeId | Int | Navigate to ResidentRelationshipTypeId | X   |
| RequestTypeId | Int | Navigate to RequestTypeId | X   |

## RequestDetail

### Example

| Owner | IdentifyNo | Description | PrevOwner | PrevIdentifyNo | PrevDescription | Fee | VehicleTypeId | Note | ResidentRequestId | ParkingFeeId | CardId | ParkingZoneId | PrevCard | PrevVehicleType | PrevParkingFee | PrevLicensePlate | LicensePlate | IsLost | CardIssueFeeTypeId |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Andrew | 0123456 | Toyota |     |     |     | 200k | OTO |     | 2   | OTO1 | H1111111 | HAM |     |     |     |     | 66655541 | True | HTE |
| Rachel | 6543210 | Huyndai | Zeto | 6789547 | Honda | 80k | OTO |     | 1   | OTO2 | E222222 | 345 | H333333 | OTO | OTO2 | 9988444 | 11133354 | False | HTH |

### Description

| Field | Type | Details | Required |
| --- | --- | --- | --- |
| Owner | String | Length: 100 |     |
| IdentifyNo | String | Length:20 |     |
| Description | String | Length:100 |     |
| PrevOwner | String | Length: 100 |     |
| PrevIdentifyNo | String | Length: 20 |     |
| PrevDescription | String | Length: 100 |     |
| Fee | Decimal |     |     |
| Note | String | Length: 200 |     |
| IsLost | Boolean | Yes/No | Default: No |
| VehicleTypeId | Int | Navigate to VehicleTypeId |     |
| ResidentRequestId | Int | Navigate to ResidentRequestId | X   |
| ParkingFeeId | Int | Navigate to ParkingFeeId |     |
| CardId | Int | Navigate to CardId |     |
| ParkingZoneId | Int | Navigate to ParkingZoneId |     |
| PrevCard | Int | Navigate to CardId |     |
| PrevVehicleType | Int | Navigate to PrevVehicleTypeId |     |
| PrevParkingFeeType | Int | Navigate to PrevParkingFeeTypeId |     |
| PrevLicensePlate | Int | Navigate to VehicleId |     |
| LicensePlate | Int | Navigate to VehicleId |     |
| CardIssueFeeTypeId | Int | Navigate to CardIssueFeeTypeId |     |