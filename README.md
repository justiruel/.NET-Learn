# .NET-Learn

misal kita ingin mengupdate sebagian file di published app : <br/>
kalau ada perubahan file dengan extension .cs maka cukup copy WaterMeters.API.dll (C:\inetpub\wwwroot\WaterMetersWebDev\bin\WaterMeters.Web.dll)<br/>
tapi kalau ada selain itu, maka copy file itu sendiri

### console.log
System.Diagnostics.Debug.WriteLine(dt.NameUser);

### Linqpad
Adalah tool untuk melakukan query dengan syntaxt LinQ 

<br/>contoh syntaxt Linq
```
from s in TRUserCoordinates
                            join u in AbpUsers.Where(p => p.IsLoged == true) on s.UserId equals u.Id
                            join d in MSDepartments.DefaultIfEmpty() on u.DepartmentId equals d.Id
                            join b in MSBeacons.DefaultIfEmpty().Where(p => p.Status == 0) on s.BeaconId equals b.Id
                            join c in MSCheckpoints on b.CheckPointId equals c.Id
                            join l in MSBuildingFloors on c.BuildingFloorId equals l.Id
                            where u.Id == 89 && l.BuildingId == 4
                            select new 
                            {
                                UserCoordinateId = s.Id,
                                PointX = c.PointX,
                                PointY = c.PointY,
                                DepartmentColor = d.Color,
                                UserId = s.UserId,
                                NameUser = u.Name,
                                DepartmentId = u.DepartmentId,
                                DepartmentName = d.DepartmentName,
                                DepartmentCode = d.DepartmentCode,
                                Image = l.Image,
                                LastUpdate = s.LastUpdate,
                                CheckPointName = c.CheckpointName
                            }
```
Dengan tool ini pula kita dapat melihat versi SQL Syntaxt dari LinQ syntaxt di atas<br/>
Ref : http://www.linqpad.net/Download.aspx
