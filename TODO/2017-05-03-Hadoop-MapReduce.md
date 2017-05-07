---
layout: post
date: 2017-05-06
title: Hadoop MapReduce
comments: true
tags: [Hadoop, MapReduce]
---

import org.apache.hadoop.mapred
public static class CountReducer extends MapReduceBase
            implements Reducer<Text, IntWritable, NullWritable,
IntWritable>

JobConf conf = new JobConf(NaievTriangleCount.class);
        conf.setJobName("trianglecount");

        conf.setOutputKeyClass(Text.class);
        conf.setOutputValueClass(NullWritable.class);


import org.apache.hadoop.mapreduce
public class DTWReducer extends Reducer<Text, DoubleWritable, Text,
DoubleWritable> {
    double min = Double.MAX_VALUE;

    @Override
    public void reduce(Text key, Iterable<DoubleWritable> records,
Context context)
            throws IOException, InterruptedException {

public int run(String[] args) throws Exception {
        Job job = Job.getInstance(getConf(), "Row Count using built in
mappers and reducers");

        job.setJarByClass(getClass());

        FileInputFormat.setInputPaths(job, new Path(args[0]));
        job.setMapperClass(DTWMapper.class);

wordCount is an good example

