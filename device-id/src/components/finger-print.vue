<template>
  <div>
    <h3>{{msg}}</h3>
    <ul>
      <li v-for="d in fingerPrint()" :key="d.uuid">{{ d }}</li>
    </ul>
  </div>
</template>

<script>
import { DeviceUUID } from "device-uuid";
export default {
  data() {
    return {
      uuid: new DeviceUUID().get(),
      du: new DeviceUUID().parse(),
    };
  },
  name: "Finger-Print",
  props: {
    msg: String,
  },
  methods: {
    fingerPrint() {
      let du = new DeviceUUID().parse();
      let dua = [
        du.language,
        du.platform,
        du.os,
        du.cpuCores,
        du.isAuthoritative,
        du.silkAccelerated,
        du.isKindleFire,
        du.isDesktop,
        du.isMobile,
        du.isTablet,
        du.isWindows,
        du.isLinux,
        du.isLinux64,
        du.isMac,
        du.isiPad,
        du.isiPhone,
        du.isiPod,
        du.isSmartTV,
        du.pixelDepth,
        du.isTouchScreen,
      ];
      var uuid = new DeviceUUID().get();
      var uuid2 = du.hashMD5(dua.join(":"));
      var uuid3 = du.hashInt(dua.join(":"));

      return [
        "Device UUID: " + uuid,
        "Fingerprint-2: " + uuid2,
        "Fingerprint-3: " + uuid3,
      ];
    },
  },
};
</script>