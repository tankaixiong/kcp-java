# kcp-java
基于skywind3000/kcp的Java版本

需实现output方法
KCP kcp = new KCP(10) {
    @Override
    protected void output(byte[] bytes, int size) {
        IoBuffer buff = IoBuffer.allocate(size);
        buff.put(bytes, 0, size);
        buff.rewind();
        session.write(buff);
    }
};