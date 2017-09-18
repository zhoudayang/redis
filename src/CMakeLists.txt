set(SERVER_FILES
  adlist.c
  ae.c
  anet.c
  dict.c
  redis.c
  sds.c
  zmalloc.c
  lzf_c.c
  lzf_d.c
  pqsort.c
  zipmap.c
  sha1.c
  ziplist.c
  release.c
  networking.c
  util.c
  object.c
  db.c
  replication.c
  rdb.c
  t_string.c
  t_list.c
  t_set.c
  t_zset.c
  t_hash.c
  config.c
  aof.c
  pubsub.c
  multi.c
  debug.c
  sort.c
  intset.c
  syncio.c
  cluster.c
  crc16.c
  endianconv.c
  slowlog.c
  scripting.c
  bio.c
  rio.c
  rand.c
  memtest.c
  crc64.c
  bitops.c
  sentinel.c
  notify.c
  setproctitle.c
  blocked.c
  hyperloglog.c
)

add_executable(redis-server ${SERVER_FILES})

set(CLIENT_FILES
  anet.c
  sds.c
  adlist.c
  redis-cli.c
  zmalloc.c
  release.c
  anet.c
  ae.c
  crc64.c
  ../deps/linenoise/linenoise.c
)

add_executable(redis-cli ${CLIENT_FILES})

set(BENCHMARK_FILES
  ae.c
  anet.c
  redis-benchmark.c
  sds.c
  adlist.c
  zmalloc.c
)

add_executable(redis-benchmark ${BENCHMARK_FILES})
